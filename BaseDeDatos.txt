create database Transporte_Publico;
use Transporte_Publico;

create table Horarios(
Id_Horarios int not null primary key unique not null auto_increment,
tiempo_trayecto varchar(40) not null,
Hora_Salida varchar(40) not null,
Hora_Llegada varchar(40) not null
);

INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("3h10m","3am","6:10am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("2h5m","3am","5:05am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("2h45m","3am","5:45am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("3h35m","3am","6:35am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("3h20m","3am","6:20am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("2h15m","3am","5:15am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("4h35m","3am","7:35am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("3h45m","3am","6:45am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("2h10m","3am","5:10am");
INSERT INTO Horarios(tiempo_trayecto,Hora_Salida,Hora_Llegada) values("1h40m","3am","4:40am");

create table Conductores(
Id_Conductor int primary key not null auto_increment,
LicenciaC varchar(5) not null
);

INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');
INSERT INTO Conductores (LicenciaC) values('Si');

      
create table Buses(
Id_bus int primary key unique not null auto_increment,
Numero_sillas int not null,
Placas varchar(40) not null
);

INSERT INTO Buses (Numero_sillas,Placas) 
values(12,'EDF456'),
	  (15,'FBH896'),
      (14,'ASH856'),
      (16,'GTH654'),
      (18,'HYR345'),
      (20,'BGD634'),
      (10,'BWR163'),
      (14,'SJK382'),
      (16,'VAR476'),
      (12,'ASD648');
      
create table Rutas(
Id_Ruta int primary key unique not null auto_increment,
Inicio_Ruta varchar(50) not null,
Fin_Ruta varchar(50) not null,
No_Paradas int not null
);

insert into Rutas (inicio_Ruta,Fin_Ruta,No_paradas)
values('BOSA SAN JOSE','PUERTO GRANDE',12),
	  ('BOSA SAN JOSE','AEROPUERTO',15),
      ('POTOSI','BOSA PIAMONTE',10),
      ('AEREOPUERTO','BOSA SAN JOSE',12),
      ('FONTIBON CENTRAL','BOSA SAN JOSE',13),
      ('VENECIA','BOSA CENTRO',14),
      ('C.C. Centro Mayor','SEVILLANA',16),
      ('CHAPINERO','ROMA',12),
      ('BOSA SAN JOSE','NUEVA DELHI',15),
      ('EGIPTO','CHAPINERO',8);
      
create table Pasajeros(
Id_Pasajeros int primary key unique not null auto_increment,
Destino varchar(50) not null,
FormaViaje varchar(30) not null
);

insert into Pasajeros(Destino,FormaViaje)
values('BOSA SAN JOSE','SENTADO'),
	  ('BOSA CENTRO','PARADO'),
      ('POTOSI','SENTADO'),
      ('NUEVA DELHI','SENTADO'),
      ('EGIPTO','PARADO'),
      ('CHAPINERO','PARADO'),
      ('C.C HAYUELOS','PARADO'),
      ('CANDELARIA','PARADO'),
      ('METROVIVIENDA','SENTADO'),
      ('BOSA SAN JOSE','SENTADO');
      
/* CONSULTAS */

/* consulta 1 */

select id_Horarios"ID_HORARIOS" from Horarios;
select id_Conductor"ID_CONDUCTOR" from Conductores;
select id_Bus"ID_BUS" from buses;
select id_Ruta"ID_RUTA" from rutas;
select id_Pasajeros"ID_PASAJEROS" from Pasajeros;

/* consulta 2 */
SELECT * FROM Horarios ORDER BY id_Horarios LIMIT 0,5;
SELECT * FROM Conductores ORDER BY id_Conductor LIMIT 0,5;
SELECT * FROM buses ORDER BY id_Bus LIMIT 0,5;
SELECT * FROM rutas ORDER BY id_Ruta LIMIT 0,5;
SELECT * FROM Pasajeros ORDER BY id_Pasajeros LIMIT 0,5;

/*select * from Horarios where id_Horarios = 1;
select * from Conductores where id_Conductor = ;
select * from buses where id_Bus = ;
select * from rutas where id_Ruta = ;
select * from Pasajeros where id_Pasajeros = ;*/

/* consulta 3 */
      
select count(*) / 2 from Horarios where id_Horarios;
select count(*) / 2 from Conductores where id_Conductor;
select count(*) / 2 from buses where id_Bus;
select count(*) / 2 from rutas where id_Ruta ;
select count(*) / 2 from Pasajeros where id_Pasajeros;

/* consulta 4 */

select * from Horarios c inner join buses s on c.id_Horarios = s.id_Bus;