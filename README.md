# JavaCampWork_Day6_Assigment2
DataBase diagram and t-sql codes


-- This script was generated by a beta version of the ERD tool in pgAdmin 4.
-- Please log an issue at https://redmine.postgresql.org/projects/pgadmin4/issues/new if you find any bugs, including reproduction steps.

<hr>

BEGIN;


CREATE TABLE public."Employers"
(
    "UserId" integer NOT NULL,
    "CompanyName" character varying(100) NOT NULL,
    "WebSite" character varying(100) NOT NULL,
    "EmailVerify" boolean NOT NULL,
    "AdminVerify" boolean NOT NULL,
    PRIMARY KEY ("UserId")
);

CREATE TABLE public."Jobs"
(
    "Id" integer NOT NULL,
    "Name" character varying NOT NULL,
    PRIMARY KEY ("Id")
);

CREATE TABLE public."Roles"
(
    "Id" integer NOT NULL,
    "Name" character varying(100) NOT NULL,
    PRIMARY KEY ("Id")
);

CREATE TABLE public."SystemPersonals"
(
    "UserId" integer NOT NULL,
    "RoleId" integer NOT NULL,
    "FirstName" character varying(100) NOT NULL,
    "LastName" character varying(100) NOT NULL,
    PRIMARY KEY ("UserId")
);

CREATE TABLE public."Users"
(
    "Id" integer NOT NULL,
    "Email" character varying(100) NOT NULL,
    "Password" character varying(50) NOT NULL,
    PRIMARY KEY ("Id")
);

CREATE TABLE public."Workers"
(
    "UserId" integer NOT NULL,
    "FirstName" character varying(100) NOT NULL,
    "LastName" character varying(100) NOT NULL,
    "NationalIdentityNumber" integer NOT NULL,
    "BirthOfYear" integer NOT NULL,
    "EmailVerifiy" boolean NOT NULL,
    PRIMARY KEY ("UserId")
);

ALTER TABLE public."Employers"
    ADD FOREIGN KEY ("UserId")
    REFERENCES public."Users" ("Id")
    NOT VALID;


ALTER TABLE public."SystemPersonals"
    ADD FOREIGN KEY ("RoleId")
    REFERENCES public."Roles" ("Id")
    NOT VALID;


ALTER TABLE public."SystemPersonals"
    ADD FOREIGN KEY ("UserId")
    REFERENCES public."Users" ("Id")
    NOT VALID;


ALTER TABLE public."Workers"
    ADD FOREIGN KEY ("UserId")
    REFERENCES public."Users" ("Id")
    NOT VALID;

END;

<hr>

![diagrammım](https://user-images.githubusercontent.com/71720425/117605549-a3eb0f80-b160-11eb-9012-cb6479fcd338.png)
