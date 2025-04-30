// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AttendanceSystem {
    address public teacher;

    mapping(address => bool) public registeredStudents;
    mapping(address => bool) public attendanceMarked;

    constructor() {
        teacher = msg.sender;
    }

    function registerStudent(address student) public {
        require(msg.sender == teacher, "Only teacher can register");
        registeredStudents[student] = true;
    }

    function markAttendance() public {
        require(registeredStudents[msg.sender], "Not a registered student");
        require(!attendanceMarked[msg.sender], "Attendance already marked");
        attendanceMarked[msg.sender] = true;
    }
}
