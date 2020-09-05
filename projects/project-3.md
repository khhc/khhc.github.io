---
layout: project
type: project
image: images/212.jpg
title: Checkbook Management Program
permalink: projects/212
# All dates must be YYYY-MM-DD format!
date: 2020-14-01
labels:
  - C
summary: A program that manages checks that I made in ICS 212.
---

At the midpoint of the ICS 212 course I was taking from Kapiolani Community College, we were tasked with making a program in the C programming language that manages the checks of a single checkbook using pointers. The program must be capable of adding a check, deleting a check, retrieving the information of a check, and printing the entire checkbook. The checks were organized in a linked list, and each check had five pieces of data attached to the object, not including the pointer to the next (if any) check. Each aforementioned task must be done through a function, and all tasks are manually selected via user input. The user must be presented with a menu to choose their choice of task for the checkbook.

```
struct check { // We initialize a structure of type check
	int check_num;
	char date[100];
	char to[100];
	float amount;
	char description[100];
	struct check *next;
};
```

I explored a minor portion of the C coding language in an earlier university course I took. Because of this, I was rather familiar with the syntax and such of how C works. However, I had no knowledge of linked lists in C prior to this class. I learned about linked lists as a data type in ICS 211, but they were structured extremely differently from C. I struggled with data types while doing this assignment, more specifically the pointers that were inputted into a function. My solution was to create a pointer of the pointer so that the original pointer was easier for me to reference, and therefore helped me understand the data types better.

```
void print_check(int check_number, struct check **checkbook) {

	if (*checkbook == NULL) { // If we've reached the end, not in checkbook
		printf("This check number is not in your checkbook.\n\n");
		return;
	}
	else if ((*checkbook)->check_num == check_number) { // If check number matches, print information
		printf("\nCheck Number: %i\n", check_number);
		printf("Check %i's Date: %s", check_number, (*checkbook)->date);
		printf("Check %i's To: %s", check_number, (*checkbook)->to);
		printf("Check %i's Amount: $%.2f\n", check_number, (*checkbook)->amount);
		printf("Check %i's Description: %s\n", check_number, (*checkbook)->description);
	}
	else if ((*checkbook)->next != NULL) { // If the next isn't NULL, traverse to it.
		print_check(check_number, &(*checkbook)->next);
	}
}
```

This assignment was my favorite of the entire course because the instructions and lessons given to us were not sufficient enough to complete this assignment. Because of that, I had to learn through the internet for the most of this task. I feel that being self-directed in that sense was an important trait to have picked up. I explored several different websites and came across a plethora of solutions, but being able to translate that from code jargon to something that I could understand was the most challenging part. This exploration of information led me to learn more about coding in C, mainly because of how the searching was driven by me rather than by an assignment for a course. I recommend taking some time to explore beyond what is asked of you for an assignment if it peaks your interest.

