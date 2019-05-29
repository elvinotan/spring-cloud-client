# Spring-Eureka-Client
Spring eureka client merupakan service/microservice yang akan mendaftarkan dirinya secara otomatis ke server eureka.

# Dependencies
Karena kita mau agar micro service ini juga konfigurasinya di handle oleh config server maka, dependencies untuk config client juga masuk, tapi apabila tidak, maka tidak perlu di masuk

Eureka Discovery</br>
Actuator</br>
Config Client</br>

# How to
1. Tambahkan @EnableDiscoveryClient pada SpringBootApplicationClass, dengan konfigurasi ini menandakan service ini ingin mendaftar dirinya pakan EurekaServer. Sebenarnya ada @EnableEurekaClient tapi kita tidak gunakan ini krn tidak semua server menggunakan eureka dan untuk amannya kita gunakan @EnableDiscoveryClient
```
@SpringBootApplication
@EnableDiscoveryClient
public class SpringEurekaClientApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringEurekaClientApplication.class, args);
	}
}
```
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

# Note
Untuk konfigurasi app ini please refer to ```https://github.com/elvinotan/config/SpringEurekaClient.yml```
Apabila konfigurasi sudah di buat di sisi config server lalukan testing berdasarkan http:{url-config-server}:{port-config-server}/{app-name}/{app-profile}
