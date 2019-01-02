# MongoDB on Atlas

## Set up an account

Follow instructions on https://cloud.mongodb.com/

## Create a DB cluster

Set replica set name. E.g. `all-in-one-mongodb-instance`

Create the first user, it will have the `atlasAdmin@admin` role associated by default.

In IP Whitelist add the trusted IP addresses which will be allowed to connect to the DB cluster.
`0.0.0.0` can be used to allow access from any IP, which is considered insecure.

## Set up Robo 3T as a client

* `Ctrl` + `N` to initiate creation of a new connection.
* On Conntection tab:
  * Choose Direct Connection for type.
  * Provide user-friendly name for the connection.
  * Set address and port of the primary server. E.g. `all-in-one-mongodb-instance-shard-00-00-xg9ig.mongodb.net` and `27017`.
* On Authentication tab:
  * Choose `admin` database.
  * Type in the main user's credentials.
  * Select `SCRAM-SHA-1` for auth mechanism.
* On SSL tab:
  * Check the Use SSL protocol box.
  * Select `Self-signed Certificate` as an authentication method.
* Test and Save the connection.
