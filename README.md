# Debug my code
 

This code is broken! When you change the pagination the next and previous buttons do not work
1. Fork the repo 
2. Attempt to debug the code to fix the issue
3. Ensure that your code works as expected
4. Post your repo back to me with an explanation of your method of debugging and how you fixed the code

# sol

The  broken code has been fixed.
The code had a problem with the pagenation. So therefore I imported ReactPaginate from "react-paginate" .
But the main problem was ,the selected number(page size) could not be displayed once the page is refreshed, which means for an event happening,  the target(the page size number) was not changing on our selection. 
( I connected it with button click property…thought something should happen when the number is clicked.The number is our target . I searched to find out if there was any property related to target in react native by using the online resources and found the target event property which I had never used before)
I experimented with target event property  and it was successful.
The target event property returns the element that triggered the event. 
event.target gives you the element that triggered the event. So, event.target.value retrieves the value of that element .

//initially the broken code was

const refreshPagination = (event) => {
    changePageSize(parseInt(event.value));
  }
  
  //fixed code 
  
  const refreshPagination = (event) => {
    changePageSize(parseInt(event.target.value));
  }
