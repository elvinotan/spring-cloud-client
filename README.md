# spring-eureka-client
Spring eureka client merupakan service/microservice yang akan mendaftarkan dirinya secara otomatis ke server eureka.

# dependencies
Karena kita mau agar micro service ini juga konfigurasinya di handle oleh config server maka, dependencies untuk config client juga masuk, tapi apabila tidak, maka tidak perlu di masuk

Eureka Discovery</br>
Actuator</br>
Config Client</br>

# how to
1. Tambahkan @EnableDiscoveryClient pada SpringBootApplicationClass, dengan konfigurasi ini menandakan service ini ingin mendaftar dirinya pakan EurekaServcer. 
