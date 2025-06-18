sp
----------------------------------
1. Insert

CREATE DEFINER=`root`@`localhost` PROCEDURE `sp_EmpInsert`(
Sp_Name NVARCHAR(200),
Sp_Address NVARCHAR(200),
Sp_Salary  DECIMAL(18,2)
)
BEGIN
INSERT INTO employee(`Name`,`Address`,`Salary`)
VALUES (Sp_Name,Sp_Address,Sp_Salary);
END

2.Select 

CREATE DEFINER=`root`@`localhost` PROCEDURE `sp_selectAll`()
BEGIN
select `Id`,`Name`,`Address`,`Salary` from `employee`;
END

3.id select

CREATE DEFINER=`root`@`localhost` PROCEDURE `sp_selectProfile`(
   Sp_Id INT
)
BEGIN
SELECT Id,Name,Address,Salary FROM Employee WHERE Id = Sp_Id;
END

4.Delete 

CREATE DEFINER=`root`@`localhost` PROCEDURE `sp_delete`(
    Sp_Id INT
)
BEGIN
    DELETE FROM Employee
    WHERE Id = Sp_Id;
END


5.update 


CREATE DEFINER=`root`@`localhost` PROCEDURE `sp_update`(
	Sp_Id INT,
    Sp_Name NVARCHAR(200),
    Sp_Address NVARCHAR(200),
    Sp_Salary DECIMAL(18,2)
)
BEGIN
    UPDATE Employee
    SET 
        Name = Sp_Name,
        Address = Sp_Address,
        Salary = Sp_Salary
    WHERE 
        Id = Sp_Id;
END
