# RSABC - 50 points
## Description

I was just listening to some relaxing ASMR when a notification popped up with this. ???

n = 57772961349879658023983283615621490728299498090674385733830087914838280699121
e = 65537
c = 36913885366666102438288732953977798352561146298725524881805840497762448828130

## Flag

```
tjctf{BOLm1QMWi3c}
```

## Solution

Soal ini mirip dengan soal Easy as RSA pada TJCTF 2019. Langkah pertama dalah melakukan faktorisasi pada `n` menggunakan [website ini](factordb.com). Faktor dari `n` disimpan dalam `p` dan `q`

```
p = 202049603951664548551555274464815496697
q = 285934543893985722871321330457714807993
```

Berikut program `rsabc.rb` yang akan digunakan pada problem kali ini.

```rb
#!/usr/bin/env ruby
require 'openssl'

# From challenge
n = 57772961349879658023983283615621490728299498090674385733830087914838280699121
e = 65537
c = 36913885366666102438288732953977798352561146298725524881805840497762448828130

# Factorised by factordb.com
p = 202049603951664548551555274464815496697
q = 285934543893985722871321330457714807993

raise "wrong factors" unless p*q == n

# Helper methods
"""
def extended_gcd(a, b)
  last_remainder, remainder = a.abs, b.abs
  x, last_x, y, last_y = 0, 1, 1, 0
  while remainder != 0
    last_remainder, (quotient, remainder) = remainder, last_remainder.divmod(remainder)
    x, last_x = last_x - quotient*x, x
    y, last_y = last_y - quotient*y, y
  end
 
  return last_remainder, last_x * (a < 0 ? -1 : 1)
end
 
def invmod(e, et)
  g, x = extended_gcd(e, et)
  if g != 1
    raise 'The maths are broken!'
  end
  x % et
end
"""

def invmod(e, et)
  e.to_bn.mod_inverse(et)
end

def powmod(x, e, n)
  x.to_bn.mod_exp(e, n)
end

def hex2ascii(text)
  [text].pack('H*')
end

# Decrypt
phi = (p-1)*(q-1)
d = invmod(e,phi)

plaintext = powmod(c, d, n)
plaintext = plaintext.to_s(16)
plaintext = hex2ascii(plaintext)
puts plaintext
```

Masukkan `n`, `e`, `c`, `p` dan `q` ke [**rsabc.rb**](./rsabc.rb). Gunakan terminal untuk menjalankan program ruby dan flag akan muncul langsung

```
$ruby rsabc.rb
```