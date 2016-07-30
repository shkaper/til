# How to add support for XPath syntax in strings (IntelliJ IDEA/Webstorm):

1. Preferences -> Editor -> Language Injections

2. "+" -> Generic JS

3. ID -> XPath

4. Places Patterns -> add new row: `+ jsLiteralExpression().withText(string().matchesBrics("//.*"))`
