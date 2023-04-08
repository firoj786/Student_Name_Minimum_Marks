# Student_Name_Minimum_Marks

package com.nt.solve.code;

import java.util.ArrayList;

import java.util.Comparator;

import java.util.List;

import java.util.Optional;

import java.util.stream.Collector;

import java.util.stream.Collectors;

/**
 * @author Firoj
 * @since 2022-01-05
 
 */

class Student3 {
	private String name;
	private int marks;

	public Student3(String name, int marks) {
		super();
		this.name = name;
		this.marks = marks;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getMarks() {
		return marks;
	}

	public void setMarks(int marks) {
		this.marks = marks;
	}

	@Override
	public String toString() {
		return "Student [name=" + name + ", marks=" + marks + "]";
	}

}

public class StudentNameMinimumMarks {

	public static void main(String[] args) {
  
		List<Student3> list = new ArrayList<Student3>();
	
		list.add(new Student3("a", 100));
    
		list.add(new Student3("b", 40));
    
		list.add(new Student3("c", 60));
    
		//String name = list.stream().sorted((o1,o2)-> o1.getMarks()-o2.getMarks()).findFirst().get().getName();
    
		 String name = list.stream().collect(Collectors.minBy(Comparator.comparing(Student3 :: getMarks))).get().getName();
     
		 System.out.println(name);
	}
  

}//b









