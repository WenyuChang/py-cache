Python Based Cache Utility
==============
In computing, a cache is a component that transparently stores data so that future requests for that data can be served faster. 
The data that is stored within a cache might be values that have been computed earlier or duplicates of original values that are 
stored elsewhere. If requested data is contained in the cache (cache hit), this request can be served by simply reading the cache, 
which is comparatively faster. Otherwise (cache miss), the data has to be recomputed or fetched from its original storage location, 
which is comparatively slower. Hence, the greater the number of requests that can be served from the cache, the faster the overall 
system performance becomes.

__Feature Supported__

1. Singleton Based Cache Module
2. User Defined Refresher
3. Cache expiration based on configurable time

Usage
============
```python
# Initialize MyCache, which is a singleton for the whole application
cache = MyCache()

# Initialize refresher for cache entry
class RefresherImpl1(Refresher):
    '''
    Refresher is called everytime specific cache entry is called but its value is expired.
    '''
    def refresh(self):
        # logic to get calculate the value of current cache entry
        return 'This is value needed cached'
refresher = RefresherImpl1()

# Add cache entry, which require cachename, its refresher and expiration time
cache.add_entry(<cache name>, refresher, '5s')

# Retrieve cache by name
value = cache.retrieve(<cache name>)
```
