Parking Lot Solution(NodeJs)
===================================

## SetUp NodeJs and Npm

Add Nodejs PPA
```
1) $ sudo apt-get install curl
2) $ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
```
Install Nodejs

  ```$sudo apt-get install nodejs```

After installing node.js verify and check the installed version.

  ```$ node -v```

also check npm version
  ```$ npm -v```
  
After installing node and npm copy and unzip parking_lot.zip file

 ``` $ cd parking_lot```

Install dependencies(Dependecy :- test framework: Mocha & chai)

```npm i```

Add execute permission:

```chmod +x index.js```

To run the application use following syntax:

```./index.js```

This will display

```
Welcome to parking_lot application.
    usage:
    
      parking_lot <filepath>: input from file
      parking_lot : interactive mode
```
Here we can see 2 Modes:
  1) File mode : Read statements from file and execute them
  2) Interactive shell mode
  
1) To use File mode use (already added the sample file provided in assignment)
     ```
      ./index.js parking_lot sample_data.txt 
     ```
Sample Response
```
Created a parking lot with 6 slots
Allocated slot number: 1
Allocated slot number: 2
Allocated slot number: 3
Allocated slot number: 4
Allocated slot number: 5
Allocated slot number: 6
Slot number 4 is free
Slot No.	Registration No		Colour
1		KA-01-HH-1234		White
2		KA-01-HH-9999		White
3		KA-01-BB-0001		Black
5		KA-01-HH-2701		Blue
6		KA-01-HH-3141		Black

Allocated slot number: 4
Sorry, parking lot is full
KA-01-HH-1234, KA-01-HH-9999, KA-01-P-333
1, 2, 4
6
Not found
```
2) To use Interactive mode:

```
     ./index.js parking_lot
```

It will display 

```
 usage:
        
            1) create_parking_lot <number_of_slots_required: creates parking lot with specific number of slots
            2) park <registration_number> <colour>: to park vehicle 
            3) leave <slot_number>: vacate slot
            4) status: provides status of parking
            5) registration_numbers_for_cars_with_colour <colour>: displays list of registration number of specific colours
            6) slot_number_for_registration_number <registration_number>: displays slot number of provided registration number
            7) slot_numbers_for_cars_with_colour <colour>: displays list of slot numbers of provided color 
            8) exit: exit
          

Provide statement or 'exit' to quit:
```

We can provide statements after this.
on entring 
```
create_parking_lot 6
```
We will get

```
Created a parking lot with 6 slots
```

We can perform the actions using the commands provided.

To perform Test for File mode and unit test use

```
npm test
```
This will provide

```
> parking_lot@1.0.0 test /Users/fur102559/nodeProj/commandLine/parking_lot
> nyc --reporter=text mocha


    Welcome to parking_lot application.
    usage:
    
      parking_lot <filepath>: input from file
      parking_lot : interactive mode
    


  Unit test
    ✓ Should return Created a parking lot with 6 slots
    ✓ Should return Allocated slot number: 1
    ✓ Should return Allocated slot number: 2
    ✓ Should return Allocated slot number: 3
    ✓ Should return Allocated slot number: 4
    ✓ Should return Allocated slot number: 5
    ✓ Should return Allocated slot number: 6
    ✓ Should return Slot number 4 is free
    ✓ Should return Status
    ✓ Should return Allocated slot number: 4
    ✓ Should return Sorry, parking lot is full
    ✓ Should return KA-01-HH-1234, KA-01-HH-9999, KA-01-P-333
    ✓ Should return 1, 2, 4
    ✓ Should return 1, 2, 4
    ✓ Should return 6
    ✓ Should return Not found
    ✓ Should return Usage
    ✓ Should return Invalid number of argument passed. max allowed argument 1
    ✓ Should return Invalid number of argument passed. max allowed argument 2
    ✓ Should return Invalid number of argument passed. max allowed argument 1
    ✓ Should return Invalid number of argument passed. max allowed argument 1
    ✓ Should return Invalid number of argument passed. max allowed argument 1
    ✓ Should return Invalid number of argument passed. max allowed argument 1

  Testing Both modes
    ✓ Should read file and run all statements

Created a parking lot with 6 slots
Allocated slot number: 1
Allocated slot number: 2
Allocated slot number: 3
Allocated slot number: 4
Allocated slot number: 5
Allocated slot number: 6
Slot number 4 is free
Slot No.	Registration No		Colour
1		KA-01-HH-1234		White
2		KA-01-HH-9999		White
3		KA-01-BB-0001		Black
5		KA-01-HH-2701		Blue
6		KA-01-HH-3141		Black

Allocated slot number: 4
Sorry, parking lot is full
KA-01-HH-1234, KA-01-HH-9999, KA-01-P-333
1, 2, 4
6

  24 passing (17ms)

Not found
---------------------|----------|----------|----------|----------|-------------------|
File                 |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Line #s |
---------------------|----------|----------|----------|----------|-------------------|
All files            |    85.84 |    75.93 |    90.48 |    85.45 |                   |
 actions.js          |      100 |     87.5 |      100 |      100 |   47,48,83,98,112 |
 file_mode.js        |      100 |       50 |      100 |      100 |                11 |
 index.js            |       75 |     62.5 |      100 |       75 |    13,14,26,27,28 |
 interactive_mode.js |    21.43 |        0 |        0 |    21.43 |... 22,23,24,25,27 |
---------------------|----------|----------|----------|----------|-------------------|
```

Directory Structure:

.
├── README.md   
├── actions.js  : contains core methods to perform operations on statements
├── file_mode.js : Handles file mode operation. This file only reads Lines from file and pass statements to actions.js
├── index.js : Initial point where we can choose modes : file mode or interactive mode
├── interactive_mode.js : Handles Interactive mode operation. This file only reads Lines from terminal and pass statements to                           actions.js
├── package-lock.json: 
├── package.json:   
├── sample_data.txt:  sample file provided in the assignment
└── test
    ├── actionsTest.js: Unit tests for code operations
    └── indexTest.js:   Testing for file mode 
    
**skppped interactive mode testcase because using same core methods and while running it asks to execute satatements to finish the coverage.





     
     
