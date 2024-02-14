# Lab 3 Report
## Bugs
We will be focusing on a test case involving the `ListExamples` class, specifically the `filter` method. The `filter` method returns a list of all the strings that contain the character 'a' in a provided list. However, the code given has a bug.
### Failure-Inducing input
```
@Test
public void testFilter() {
        List<String> names = new ArrayList<String>();
        names.add("Brandon");
        names.add("Adrian");
        names.add("Yuwei");
        List<String> result = ListExamples.filter(names, new ListExamples());
        List<String> expected = new ArrayList<String>();
        expected.add("Brandon");
        expected.add("Adrian");
        assertEquals(expected, result)
}
```
### Valid Input
```
@Test
public void testFilter2() {
        List<String> names = new ArrayList<String>();
        names.add("Eric");
        List<String> result = ListExamples.filter(names, new ListExamples());
        List<String> expected = new ArrayList<String>();
        assertEquals(expected, result);
}
```
### Symptom
![Image](symptom.png)
