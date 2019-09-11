# Distributed database
Distributed database permissions layer


## Abstract
A distributed database system, that has different permission levels,
but main thing is that for things that modify any data like write/update/delete,
the cluster of applications must give consensus before it is accepted.
Essenstially very similiar to a block chain, but instead of having things like proof of work and all implemented, this is essentially
a mysql or something similiar that is replicated across many nodes to provide resilience
and also have customisable level of security and CRUD permissions

Basically this allow you to seperate the computation and storage of your dApps
So in the traditional sense, it is like having a DBaaS handle your storage and instead of the server having control over the data,
the creator has control of the CRUD permissions,
and the cluster of users have control of the other data as defined by the permissions as specified by the dApp


## Pain Points to solve





## Technical details
### How to connect to the DB
Using the API directly, or using a SDK that wraps over all the API.
Create your DB, get the API Key and all, put it into the API/SDK and start using/connecting to your database

### Permissions
Once it is set at the start of the project, it can never ever be changed

### Storage
How and where the data is stored is not really restricted by this project
This project is the middle point between your application code and the database, giving it an additional permissions layer

The data itself is stored by traditional storage means and all

You can store the data either in places like DBaaS from Google/AWS or things like file storage, or even using IPFS to store your data to your apps users.

THe whole point is how the data is written to the DB, the operations to the DB goes through the permissions layer which is this software before it goes to the DB and how your DB setup deals with the data is up to you.


Essentially you can connect all your apps to this permissions layer and connect this permissions layer on top of any type of database that you would want.
Meaning that instead of using the mySQL connector, you will use the "repo name"-mySQL connector, which is basically the mySQL connector with a wrapper over it to implement the permissions layer.
Also if you do not want to use those, we recommend our very own distributed database software that you can use. It is essentially a database that has this permission layer already built in, so when you use it, you can just treat the permission layer as if it is the database directly.
This will be a direct wrapping using the permissions layer, so that it will be "more secure" as there isn't any additional connection overhead to a database as this becomes the database.




## Use Case
So instead of configuring all your different database in your polyglot persistence system to have the same permissions set and needing to learn all of them, this gives you kinda of like a central control of the permissions, where you can control everything on this layer.