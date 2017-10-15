# erpnext
Thanks davidgu

Erpnext docker image

* Based on: debian
* Including services: 
  * Redis
  * Nginx
  * memcached
  * Maridb
  * cron
 
Install with:

`docker run -d -p 80:80 --name erpnext -v /site1.local:/home/frappe/frappe-bench/sites/site1.local/ -v /mysql:/var/lib/mysql babim/erpnext`

## run data container
`docker create -v /home/frappe/frappe-bench/sites/site1.local/ -v /var/lib/mysql --name erpdata babim/erpnext`

## run erpnext
`docker run -d -p 80:80 --name erpnext --volumes-from erpdata davidgu/erpnext`

## get passwords
`docker exec -ti erpnext cat /root/frappe_passwords.txt`

Login on http://localhost with Administrator / password
