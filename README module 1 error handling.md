# smart contract project 
We created a contract to handle different statements in solidity example (require(),assert(),revert())

## Description

This is project created to demonstrate the usage of require(),assert(),revert() statement .
In this project i am creating a  contract to manage the enrollment of the student who want to enroll in the academics . They have to give their name ,grade , age .And have to satisfy the condition like name couldnot be of length zero etc.

## Getting Started

### Installing

* to deploy this code you need to have remix or any IDE.
* need compiler for solidity 
* required version of solidity compiler is (version ^0.8.0)

### Executing program

*to deploy this block of code you need an IDE of  solidity
* after that copy paste the given block of code in your IDE
* then set compiler to version (0.8.0)
* then deploy the assertsol contract
* then implement the summation function
* the require()statement ensures that father age should not be zero
* the assert() statement ensures that the father age shoul be greater than son's age 
* the revert()statement check the difference of father and son age and if the differnce is less than 10 revert with and error mesage .


// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract School {
    struct Student {
        string name;
        uint age;
        uint grade;
    }

    Student[] public students;

    function enrollStudent(string memory _name, uint _age, uint _grade) public {
        // Require that the student's age is between 6 and 18 years.
        require(_age >= 6 && _age <= 18, "Student age must be between 6 and 18.");

        // Assert that the student's grade is appropriate (1 to 12).
        assert(_grade >= 1 && _grade <= 12);

        // Revert if the student's name is empty.
        if (bytes(_name).length == 0) {
            revert("Student name cannot be empty.");
        }

        // Enroll the student if all conditions are met.
        students.push(Student(_name, _age, _grade));
    }

    function getStudent(uint index) public view returns (string memory, uint, uint) {
        require(index < students.length, "Student index is out of bounds.");
        Student memory student = students[index];
        return (student.name, student.age, student.grade);
    }
}


## Help
* make sure your IDE is for solidity 
*  make sure your compiler is set to version (0.8.0) otherwise error will throw
* make sure you safe search in brave browser is off 

## Authors
Amrita Kumari


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
