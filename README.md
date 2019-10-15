# The stuff of subject web services

This repository includes mutants, source code, and test cases of subjects web services used in paper titled "Dynamic Random Testing of Web Services:
A Methodology and Evaluation".

## mutants

All used mutants of *ACMS*, *CUBS*, and *PBS* can be found in the *mutants* directory. 

## source code 

We developed *ACMS*, *CUBS*, and *PBS* according to real-life specification, and wrote them in Java. Those scripts can be found in the *source code* directory, in which the following stuff can be found.

| Directory | Content                                   | Message    |
| --------- | ----------------------------------------- | ---------- |
| *ACMS*    | BaggageController.java and Passanger.java | Main Class |
| *CUBS*    | ChinaUnionBill.java                       | Main Class |
| *PBS*     | ParkingFeeCalculator.java                 | Main Class |

## test pool

We made use of random testing technique to generate test cases for *ACMS*, *CUBS*, and *PBS*. In the *test pool* directory, we have developed scripts for generating test cases.  For instance, the main method of script generating test cases for *ACMS*   is named "generateTestcases", which is shown as follow.

``

public List<Bean> generateTestCase(int seed, int numberOfTestCase){

​	Random random = new Random(seed);

​	DecimalFormat decimalFormat = new DecimalFormat("#.00");

​	List<Bean> tempbeans = new ArrayList<Bean>();

​	for (int i = 0; i < numberofTestCase; i++){

​		String airlineType = String.valueOf(random.nextInt(2));

​		Stirng cabinClass = String.valueOf(random.nextInt(3));

​		String passagerCatagory = String.valueOf(random.nextInt(4));

​		String baggageWeight = String.valueOf(decimalFormat.format(random.nextDouble() * 60));

​		String ID = String.valueOf(i + 1);

​		Bean bean =new Bean();

​		bean.setvariables(ID, 		airlineType,cabinClass,passagerCategory,baggageWeight);

​		tempbeans.add(bean);

​	}

​	return tempbeans;

}

``

The *seed* parameter is used for generating test cases; And the *numberOfTestCase* represents the number of test cases that will be generated.