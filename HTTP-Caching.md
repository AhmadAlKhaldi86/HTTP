# HTTP caching
   - Reusing previously fetched resources.
   
### caching control : Cache-Control prop
- Cache-Control: no-store --> Every time you need to fetch from server. 
- Cache-Control: no-cache --> Use chache but vaidate from server when gets a request. 
- Cache-Control: private  --> Use Cache 
- Cache-Control: public   --> Use Cache 
- Cache-Control: max-age=31536000 --> In seconds fresh vs stale . 
- Cache-Control: must-revalidate --> If expired or fresh. 

### Freshness: 
