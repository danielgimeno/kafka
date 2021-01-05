# kafka

Read details in http://www.danielgimeno.org/article/Introduccion-a-kafka

## Installation

Docker Kafka Installation:  

git clone https://github.com/danielgimeno/kafka


Note: Don't forget to set up your IP of your Docker host before executing docker compose, and the conexion between producers and consumers with Kafka server.  


### Productor
Python packages needed:  

pip3 install fake  
pip3 install kafka


### Consumer  
sudo apt-get update -y  
sudo apt-get install -y librdkafka-dev  
sudo pecl install rdkafka  

Enable PHP-extension in PHP config. Add to php.ini:

sudo nano /etc/php/7.4/cli/php.ini  

extension=rdkafka.so  

Restart apache server:  

sudo service apache2 restart  

## Run  

### run Kafka environment:  

docker-compose up

### run producer:  

python3 producer.py  

### run consumer:   

php consumer.php  


