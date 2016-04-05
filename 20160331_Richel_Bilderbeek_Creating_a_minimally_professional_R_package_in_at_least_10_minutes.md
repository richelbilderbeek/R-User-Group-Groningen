# Creating a minimally professional R package in at least 10 minutes

 * Date: 2016-03-31
 * Speaker: Richel Bilderbeek

The R function:

```
#' Multiplies a value by 2, except 42, which it will multiply by 1
#' @param x Input value
#' @return Magicified value
#' @export
do_magic <- function(x) {
  if (x == 42) {
    return 42
  }
  z <- x * 2
  z
}
```

My `lintr` test:

```
test_that("Package must pass lintr", {
  lintr::expect_lint_free()
})
```

The commands I used:

```
devtools::add_test("do_magic") # It will prepend the filename with 'test-'
devtools::add_vignette("demo_do_magic")
devtools::check()
```

