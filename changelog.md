2016-01-24 - 0.1.4

- include source info in preamble of generated file
- consider all java keywords and special literals to generate valid identifier

2016-01-11 - 0.1.3
 
- generate code for java 8 by default.
  Found out that Typesafe Config's `hasPath` method returns `false` for actually existing paths that just
  happen to be defined with `null`!  So, `hasPathOrNull` is now used in the generated code, and this method 
  is only available in Typesafe Config 1.3.0+, which requires Java 8.
  The new flag `--j7` makes the tool generate `hasPath` checks instead of `hasPathOrNull`, 
  so the generated code can be used with Typesafe Config 1.2.1 and Java <= 7.
 