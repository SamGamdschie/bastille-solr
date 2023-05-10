# bastille-solr
Apache Sole Full-Text- Search Index for Dovecot via Bastille

see https://doc.dovecot.org/configuration_manual/fts/solr/#fts-backend-solr

```sh
/etc/crontab
15 2 * * *  solr /usr/local/bin/curl -s 'http://localhost:8983/solr/dovecot/update?optimize=true' > /dev/null
*/5 * * * * solr /usr/local/bin/curl -s 'http://localhost:8983/solr/dovecot/update?commit=true' > /dev/null
```