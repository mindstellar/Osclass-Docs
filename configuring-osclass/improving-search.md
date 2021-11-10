# Improving Search

## Improving search <a href="firstheading" id="firstheading"></a>

MySQL's full-text search capability has few user-tunable parameters.

{% hint style="warning" %}
**NOTE:**Note that full-text search is carefully tuned for the most effectiveness. Modifying the default behavior in most cases can actually decrease effectiveness. Do not alter the MySQL sources unless you know what you are doing.
{% endhint %}

For Osclass users, item title and item description have a fulltext index, that do search more effective and speed up.

The minimum and maximum lengths of words to be indexed by default is 4 (4 characters), that means, only words more or equal than 4 will be indexed.

### Changing the maximum, minimum limit

If you like to change the minimum and maximum lengths of words to be indexed, you need update your mysql config file.

```
[mysqld]
ft_min_word_len=3
```

```
[mysqld]
ft_max_word_len=10
```

### Rebuilding FULL-Text Index

After this, if you modify full-text variables that affect indexing (ft\_min\_word\_len, ft\_max\_word\_len, or ft\_stopword\_file), you must rebuild your FULL-TEXT indexes after making the changes and restarting the server. To rebuild the indexes in this case, it is sufficient to do a QUICK repair operation:

```sql
REPAIR TABLE tbl_name QUICK;
```

{% hint style="warning" %}
Replace `tbl_name` with your table name. e.g oc\_t\_item\_description.
{% endhint %}

\
Source: Fine-Tuning MySQL Full-Text Search[\[1\]](http://dev.mysql.com/doc/refman/5.1/en/fulltext-fine-tuning.html)
