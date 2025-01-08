```java 


import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class StrongTagMatcher {
    public static void main(String[] args) {
        // Regex pattern to match a <strong> tag with optional attributes
        String regex = "<strong\\b[^>]*>";

        // Test strings
        String[] testStrings = {
            "<strong>",
            "<strong class=\"highlight\">",
            "<strong id=\"main\" class=\"highlight\">",
            "<strong data-custom=\"value\">",
            "<strong><em>text</em></strong>",  // This should not match
            "<b>text</b>"  // This should not match
        };

        // Compile the regex pattern
        Pattern pattern = Pattern.compile(regex);

        // Match each test string against the pattern
        for (String testString : testStrings) {
            Matcher matcher = pattern.matcher(testString);
            if (matcher.find()) {
                System.out.println("Matched: " + testString);
            } else {
                System.out.println("Did not match: " + testString);
            }
        }
    }
}
```