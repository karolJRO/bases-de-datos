/bases-de-datos/
create table locales(
    mercancia varchar(50) primary key,
    capacidad varchar(20),
    experiencia_trabajadores boolean,
    clientes_viajes varchar(20),
);

create table marcas(
    calidad varchar(20) primary key,
    nombres varchar(10),
);
       
create table trabajadores(
    experiencia boolean primary key,
    disenadores varchar(50),
    mercancia_locales varchar(50),
);

create table viajes(
    clientes varchar(20) primary key,
    fechas date,
);

create table marcas(
    mercancia_locales varchar(50),
    nombre_marca varchar(50),
    fecha_hora date,

    primary key(mercancia_locales,nombre_marca,fecha_hora)
);

alter table locales
add foreign key (clientes_viajes) 
references viajes(clientes);

alter table marcas 
add foreign key (nombre_marca) 
references marca(nombre);

alter table trabajadores
add foreign key (experiencia_trabajadores)
references trabajadores(experiencia);

alter table locales
add foreign key (mercancia_locales)
references locales(mercancia);
