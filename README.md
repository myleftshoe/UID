#### Simple usage

```
const uid = new UID().value
```

generates a 8 char uid from the charset `23456789abdegjkmnpqrvwxyz`

#### Alpha only

```
import UID, { alpha } from './uid.js'

const uid = new UID({ charset: alpha, length: 6 }).value
```

generates a 6 char uid from the charset `'bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ'`

#### Custom charset

```
const uid = new UID({ charset: '!@#$%^&*()_+', length: 4 }).value
```

#### Ensure unique 

```
const uid = new UID().exclude([Array of uids to exclude]).value 
```

#### Notes 

1. The included charsets `safe` and `alpha`, exclude vowels to prevent expletives
2. No restrictions are placed on the length or charsets you provide. You could for example pass `{ charset: 'x', length:1 }`  which will of course only ever generate a uid of 'x'.
3. If you provide an exclude array the code will keep looping until it finds a uid that is not in the array. If the array is too large and/or the charset and length provided are not sufficient it may take some time or enter an infinite loop.  
