crypto-pubkey-openssh
=====================

OpenSSH keys decoder/encoder, example.

```haskell
import System.Environment (getArgs)
import qualified Data.ByteString as B

import Crypto.PubKey.OpenSsh (decodePrivate)

main :: IO ()
main = do
    fname <- fmap head getArgs
    content <- B.readFile fname
    case decodePrivate content of
        Left e -> error e
        Right key -> print key
```
