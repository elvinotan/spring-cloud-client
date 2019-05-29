# spring-eureka-client
Spring eureka client merupakan service/microservice yang akan mendaftarkan dirinya secara otomatis ke server eureka.

# dependencies
Karena kita mau agar micro service ini juga konfigurasinya di handle oleh config server maka, dependencies untuk config client juga masuk, tapi apabila tidak, maka tidak perlu di masuk

Eureka Discovery</br>
Actuator</br>
Config Client</br>

# how to
1. Tambahkan @EnableDiscoveryClient pada SpringBootApplicationClass, dengan konfigurasi ini menandakan service ini ingin mendaftar dirinya pakan EurekaServcer. 
2. Buatlah bootstrap.yml sebagai pengganti application.properties
```
--- 
spring:
  application:
    name: SpringEurekaClient
  cloud:
    config:
      uri: http://localhost:9080
      failFast: false
```
Snippet di atas menandakan, aplikasi ini bernama SpringEurekaClient dan mohon load konfigurasi dari Spring Config yang configurasinya berdama SpringEurekaClient.yml
