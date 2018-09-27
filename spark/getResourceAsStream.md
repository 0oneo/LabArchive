### Background

In maven project, I want to read some txt files in resouces directory from my spark jar app. the code is like below

```java
rdd.map(...) {
  ... {
    // flowing code is under spark context
    StringBuffer content = new StringBuffer();
    InputStream inputStream = getClass().getResourceAsStream(file_name)
    BufferedReader br = new BufferedReader(new InputStreamReader(inputStream));
    for (String line; (line = br.readLine()) != null; ) {
      content.append(line + System.lineSeparator());
    }
  }
}

```

### Expected result
can access the `file_name`'s content under jar's package.

### Actual result
raise a `NullException` 

### Reason
Don't known currently.
