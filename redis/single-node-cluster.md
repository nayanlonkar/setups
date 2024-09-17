#Redis single node cluster setup

## MacOS
1. Install redis  
    > brew install redis

2. Append following lines to redis.conf file (`/opt/homebrew/etc/redis.conf`)
    > port 6379  
    > cluster-enabled yes  
    > cluster-config-file nodes.conf  
    > cluster-node-timeout 5000  
    > appendonly yes  

3. Start the redis service. 
    > To start  - $ brew services start redis
    > To stop   - $ brew services stop redis
    > To status - $ brew services info redis

4. To check cluster nodes use
    > redis-cli -p 6379  cluster nodes

5. To cover all the slots, use
    > redis-cli --cluster fix localhost:6379