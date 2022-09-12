# Spring Secure Login by jwt authentication with rolewise privilage
<p>
  <h3>Spring Boot Security Login example with JWT and H2 database</h3> 
<p/>

<p>
  <ul>
    <li>Appropriate Flow for User Login and Registration with JWT</li>
    <li>Spring Boot Rest Api Architecture with Spring Security</li>
    <li>How to configure Spring Security to work with JWT</li>
    <li>How to define Data Models and association for Authentication and Authorization</li>
    <li>Way to use Spring Data JPA to interact with H2 Database</li>
  </ul>
</p>

<p>
  <h3>User Registration, Login and Authorization process.</h3>
</p>

<p>
  <a href="https://www.joyee.com/">
    <img alt="Qries" src="https://github.com/bezkoder/spring-boot-security-login/blob/master/spring-boot-security-login-jwt-flow.png" width=700" height="400">
  </a>
</p>

<p>
  <h3>Spring Boot Server Architecture with Spring Security</h3>
</p>

<p>
  You can have an overview of our Spring Boot Server with the diagram below:
</p>

<p>
  <a href="https://www.joyee.com/">
    <img alt="Qries" src="https://github.com/bezkoder/spring-boot-security-login/blob/master/spring-boot-security-login-jwt-architecture.png" width=700" height="400">
  </a>
</p>

<p>
  <h3>Dependency</h3>
  to user h2 database
</p>
<pre>
  &lt;<span class="pl-ent">dependency</span>&gt;
    &lt;<span class="pl-ent">groupId</span>&gt;com.h2database&lt;/<span class="pl-ent">groupId</span>&gt;
    &lt;<span class="pl-ent">artifactId</span>&gt;h2&lt;/<span class="pl-ent">artifactId</span>&gt;
    &lt;<span class="pl-ent">scope</span>&gt;runtime&lt;/<span class="pl-ent">scope</span>&gt;
  &lt;/<span class="pl-ent">dependency</span>&gt;
</pre>

<p>
  for jwt
</p>

<pre>
  &lt;<span class="pl-ent">dependency</span>&gt;
    &lt;<span class="pl-ent">groupId</span>&gt;io.jsonwebtoken&lt;/<span class="pl-ent">groupId</span>&gt;
    &lt;<span class="pl-ent">artifactId</span>&gt;jjwt&lt;/<span class="pl-ent">artifactId</span>&gt;
    &lt;<span class="pl-ent">version</span>&gt;0.9.1&lt;/<span class="pl-ent">version</span>&gt;
  &lt;/<span class="pl-ent">dependency</span>&gt;
</pre>

<p>
  for spring security
</p>

<pre>
  &lt;<span class="pl-ent">dependency</span>&gt;
    &lt;<span class="pl-ent">groupId</span>&gt;org.springframework.security.oauth&lt;/<span class="pl-ent">groupId</span>&gt;
    &lt;<span class="pl-ent">artifactId</span>&gt;spring-security-oauth2&lt;/<span class="pl-ent">artifactId</span>&gt;
    &lt;<span class="pl-ent">version</span>&gt;2.0.2.RELEASE&lt;/<span class="pl-ent">version</span>&gt;
  &lt;/<span class="pl-ent">dependency</span>&gt;
</pre>

<p>
  <h3>Configure Spring Datasource, JPA, App properties</h3>
  Open <code>src/main/resources/application.properties</code>
</p>

<p>
  <code>
    spring.h2.console.enabled=true
    spring.h2.console.path=/h2-ui
    
    spring.datasource.url=jdbc:h2:file:./testdb</br>
    spring.datasource.driverClassName=org.h2.Driver</br>
    spring.datasource.username=sa</br>
    spring.datasource.password=</br>

    spring.jpa.show-sql=true</br>
    spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.H2Dialect</br>
    spring.jpa.hibernate.ddl-auto= update</br>

    # App Properties</br>
    bezkoder.app.jwtCookieName= bezkoder</br>
    bezkoder.app.jwtSecret= bezKoderSecretKey</br>
    bezkoder.app.jwtExpirationMs= 86400000</br>

    server.port=9310
  </code>
</p>




