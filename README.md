# tap-postgres

### Install and Run

Ensure poetry is installed on your machine. 

- This command will return the installed version of poetry if it is installed.
```
poetry --version
```

- If not, install poetry using the following commands (from https://python-poetry.org/docs/#installation):
```
curl -sSL https://install.python-poetry.org | python3 -
PATH=~/.local/bin:$PATH
```

Within the `tap-postgres` directory, install dependencies:
```
poetry install
```

Then run the tap:
```
poetry run tap-postgres <options>
```

## set rds.logical_replication in parameter(reboot)= 1

This should also set `max_wal_senders && max_replication_slots > 0`

Singer tap for PostgreSQL supporting Full Table & Logical Replication
using the wal2json decoder plugin.

```
SELECT * FROM pg_create_logical_replication_slot('stitch', 'wal2json');
```

---

Copyright &copy; 2018 Stitch
