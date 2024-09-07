MYSQL DUMP

Usage: mysqldump [OPTIONS] database [tables]
mysqldump -u root -p --all-databases > all_database.sql

Run MYSQL Data Base Container

docker run -itd -e MYSQL_ROOT_PASSWORD=YOUR_PASSWORD --name mysqldata -v test:/var/lib/mysql mysql:5.6.48

ADD REPO IN CONATINER AND move apt-get install

echo "deb http://archive.debian.org/debian stretch main contrib non-free" > /etc/apt/sources.list
echo "deb-src http://archive.debian.org/debian stretch main contrib non-free" >> /etc/apt/sources.list

echo 'Acquire::Check-Valid-Until "false";' > /etc/apt/apt.conf

apt-get update