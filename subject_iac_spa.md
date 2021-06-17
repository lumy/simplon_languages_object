
# Subject

You should write a frontend and a backend applications.

Frontend has to be done with reactjs (or vuejs but not angular).
Backend can be wrote in any languages (avoid python, you already know it).

# Rest: Backend

Your backend will *simulate* a Cloud.
Authentification has to be implemented

You should have a databases (any kind of databases will be fine).
The rout should include:

  /api/iac/server <= manage servers
  /api/iac/ip <= manage ips
  /api/iac/docker <= manage docker instances.
  /api/account/facture <= manage facture.
  /api/account/profil <= manage profile user.

`/api/iac/server`:
  GET: return the list of currents server
`/api/iac/server/create`:
  GET: return all available data for creating a new server (os,space disk, proc....)
  POST: create a new server with data from requests.

`/api/iac/server/<uid>`:
  GET: return data about the specifique server (uptime, creation_date, capacity/procs...)
  POST: update a server with new configuration

`/api/iac/ip`:
  GET: return the list of ips attached to my account
  POST: request a new ip for my account.

`/api/iac/docker`:
  GET: return a list of docker instance that are running

`/api/iac/docker/<uid>`:
  GET: return data about the docker instances.
  POST: restart the current docker instances.

`/api/iac/docker/create`:
  POST: create a new docker instance.

`/api/account/facture`:
  GET: return the bills to be payed.
  Post: let the client pay with a credit card.

`/api/account/profil`:
  GET: Return data about the current auth user.
  POST: update data for auth user.



The server and docker instances should be simulated (not point to create a real instance behind) but
you should keep a trace of everything, so if i create a servers, i should know when i created it,
since how long it has been running, how many rams do i have etc... etc...
All IPs should be fakes ones but still, i should have have twice the same ip (so a post on
`api/iac/ip` should always return a new value).


# SPA: Frontend

You should all do in the same WebPage,

The design is let to your attention, as long as we can use it easily.
