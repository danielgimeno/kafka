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

## Result:  

Runing the producer:  

 ✘ daniel@dockerserver  ~/proyectos/kafkaprod  python3 producer.py  
{'name': 'Shelia Morgan', 'address': '3169 Jenna Lights\nNorth Carla, OR 24599', 'created_at': '2015'}  
{'name': 'Sara Hart', 'address': 'PSC 6266, Box 0588\nAPO AE 06432', 'created_at': '2005'}  
{'name': 'Joseph Best', 'address': '433 Ortiz Falls\nMontoyafurt, DC 33980', 'created_at': '1997'}  
{'name': 'Corey Daugherty', 'address': '27170 Knight Court Suite 884\nMichaelfurt, SC 26691', 'created_at': '1989'}  
  
Running the consumer:  
  
daniel@dockerserver  ~/proyectos/php-rdkafka-consumer  php consumer.php  
object(RdKafka\Message)#5 (8) {  
  ["err"]=>  
  int(0)  
  ["topic_name"]=>  
  string(9) "fakeusers"  
  ["timestamp"]=>  
  int(1609802723400)  
  ["partition"]=>  
  int(0)  
  ["payload"]=>  
  string(102) "{"name": "Shelia Morgan", "address": "3169 Jenna Lights\nNorth Carla, OR 24599", "created_at": "2015"}"  
  ["len"]=>  
  int(102)  
  ["key"]=>  
  NULL  
  ["offset"]=>  
  int(0)  
}  
object(RdKafka\Message)#6 (8) {  
  ["err"]=>  
  int(0)  
  ["topic_name"]=>  
  string(9) "fakeusers"  
  ["timestamp"]=>  
  int(1609802727402)  
  ["partition"]=>  
  int(0)  
  ["payload"]=>  
  string(90) "{"name": "Sara Hart", "address": "PSC 6266, Box 0588\nAPO AE 06432", "created_at": "2005"}"  
  ["len"]=>    
  int(90)  
  ["key"]=>  
  NULL   
  ["offset"]=>  
  int(1)  
}  
object(RdKafka\Message)#5 (8) {  
  ["err"]=>  
  int(0)  
  ["topic_name"]=>  
  string(9) "fakeusers"  
  ["timestamp"]=>  
  int(1609802731409)  
  ["partition"]=>  
  int(0)  
  ["payload"]=>  
  string(98) "{"name": "Joseph Best", "address": "433 Ortiz Falls\nMontoyafurt, DC 33980", "created_at": "1997"}"  
  ["len"]=>  
  int(98)  
  ["key"]=>  
  NULL  
  ["offset"]=>  
  int(2)   
}  
No more messages; will wait for more  
object(RdKafka\Message)#5 (8) {  
  ["err"]=>  
  int(0)  
  ["topic_name"]=>  
  string(9) "fakeusers"  
  ["timestamp"]=>  
  int(1609802735413)  
  ["partition"]=>  
  int(0)  
  ["payload"]=>  
  string(115) "{"name": "Corey Daugherty", "address": "27170 Knight Court Suite 884\nMichaelfurt, SC 26691", "created_at": "1989"}"  
  ["len"]=>  
  int(115)  
  ["key"]=>  
  NULL   
  ["offset"]=>  
  int(3)  
}  

