# I can't connect to MySQL \(SSL & Authorization\)<a name="troubleshoot-connect-mysql"></a>

 To check on some common connection issues in MySQL, follow the steps described here\. This procedure helps you find out if you have enabled SSL and granted usage rights\.

1. First, check /etc/my\.cnf to make sure SSL is enabled for MySQL\.

   Then, go into MySQL and run:

   ```
   show status like 'Ssl%';
   ```

   These results show that SSL is working:

   ```
   +--------------------------------+----------------------+
   | Variable_name                  | Value                |
   +--------------------------------+----------------------+
   | Ssl_accept_renegotiates        | 0                    |
   | Ssl_accepts                    | 1                    |
   | Ssl_callback_cache_hits        | 0                    |
   | Ssl_cipher                     |                      |
   | Ssl_cipher_list                |                      |
   | Ssl_client_connects            | 0                    |
   | Ssl_connect_renegotiates       | 0                    |
   | Ssl_ctx_verify_depth           | 18446744073709551615 |
   | Ssl_ctx_verify_mode            | 5                    |
   | Ssl_default_timeout            | 0                    |
   | Ssl_finished_accepts           | 0                    |
   | Ssl_finished_connects          | 0                    |
   | Ssl_session_cache_hits         | 0                    |
   | Ssl_session_cache_misses       | 0                    |
   | Ssl_session_cache_mode         | SERVER               |
   | Ssl_session_cache_overflows    | 0                    |
   | Ssl_session_cache_size         | 128                  |
   | Ssl_session_cache_timeouts     | 0                    |
   | Ssl_sessions_reused            | 0                    |
   | Ssl_used_session_cache_entries | 0                    |
   | Ssl_verify_depth               | 0                    |
   | Ssl_verify_mode                | 0                    |
   | Ssl_version                    |                      |
   +--------------------------------+----------------------+
   ```

   If SSL is disabled, the result looks like this:

   ```
   +--------------------------------+-------+
   | Variable_name                  | Value |
   +--------------------------------+-------+
   | Ssl_accept_renegotiates        | 0     |
   | Ssl_accepts                    | 0     |
   | Ssl_callback_cache_hits        | 0     |
   | Ssl_cipher                     |       |
   | Ssl_cipher_list                |       |
   | Ssl_client_connects            | 0     |
   | Ssl_connect_renegotiates       | 0     |
   | Ssl_ctx_verify_depth           | 0     |
   | Ssl_ctx_verify_mode            | 0     |
   | Ssl_default_timeout            | 0     |
   | Ssl_finished_accepts           | 0     |
   | Ssl_finished_connects          | 0     |
   | Ssl_session_cache_hits         | 0     |
   | Ssl_session_cache_misses       | 0     |
   | Ssl_session_cache_mode         | NONE  |
   | Ssl_session_cache_overflows    | 0     |
   | Ssl_session_cache_size         | 0     |
   | Ssl_session_cache_timeouts     | 0     |
   | Ssl_sessions_reused            | 0     |
   | Ssl_used_session_cache_entries | 0     |
   | Ssl_verify_depth               | 0     |
   | Ssl_verify_mode                | 0     |
   | Ssl_version                    |       |
   +--------------------------------+-------+
   ```

1. Make sure you have installed a supported SSL certificate on the database server\. 

1. Grant usage for the specific user to connect using SSL\.

   ```
   GRANT USAGE ON *.* TO 'encrypted_user'@'%' REQUIRE SSL;                        
   ```

Please see the following for more detail on the solution in this example:

+ [SSL Support for MySQL DB Instances](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html#MySQL.Concepts.SSLSupport.html)

+ [Using SSL to Encrypt a Connection to a DB Instance](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.SSL.html)

+ [MySQL documentation](https://dev.mysql.com/doc/refman/5.6/en/secure-connections.html)