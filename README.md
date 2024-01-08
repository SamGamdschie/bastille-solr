# bastille-solr
Apache Sole Full-Text- Search Index for Dovecot via Bastille

see https://doc.dovecot.org/configuration_manual/fts/solr/#fts-backend-solr

## Cronjob
Create two contrab entries for user solr ```crontab -u solr -e```:
```sh
15 2 * * *  /usr/local/bin/curl -s 'http://localhost:8983/solr/dovecot/update?optimize=true' > /dev/null
*/5 * * * * /usr/local/bin/curl -s 'http://localhost:8983/solr/dovecot/update?commit=true' > /dev/null
```

## Adjusted Schema
Check GitHub for current versions of SOLR schema and config at https://github.com/dovecot/core/tree/main/doc
