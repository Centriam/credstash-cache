credstash cache
===============

`credstash-cache` is a small utility to keep secrets loaded from credstash in memory
in order to reduce the number of calls to DynamoDB and KMS for the same secrets.


## Installation
`pip install credstash-cache`


## Usage
To load a secret from the default `credential-store` table
```
from credstash_cache import get_secret

secret = get_secret('credstash_key')
```

To load a secret from a non-default credstash table called `my-secret-table`
```
from credstash_cache import get_secret

# using positional arguments
secret = get_secret('credstash_key', 'my-secret-table')

# or you can explicitly use the table parameter name
secret = get_secret('credstash_key', table='my-secret-table')
```

To load a secret from the non-default `us-east-1` region
```
from credstash_cache import get_secret

secret = get_secret('credstash_key', region='us-west-1')
```

To load a secret from the non-default `us-east-1` region and a non-default table called `my-secret-table`
```
from credstash_cache import get_secret

# using positional arguments
secret = get_secret('credstash_key', 'my-secret-table', 'us-west-1')

# using parameter names
secret = get_secret('credstash_key', table='my-secret-table', region='us-west-1')
```

## Issues
If you have questions or have trouble using the app please file a bug report
at:

https://github.com/centriam/centriam-credstash/issues
