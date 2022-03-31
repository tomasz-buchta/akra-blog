---
layout: post
title:  "Ruby splat operator"
date:   2022-03-17 09:33:15 +0100
categories: til ruby
---

# Ruby splat `*` and double splat `**` operator

You can use splat operator to 'unwrap' array as separate arguments
```ruby
def sum(*nums)
  nums.reduce(:+)
end

numbers = [1, 5, 6]

sum(1,5,6)
# => 12
sum(*numbers)
# => 12
# This will not sum up the numbers since it will treat it as a single argument
sum(numbers)
# => [1, 5, 6]
```

You can use double splat operator `**` to unwrap hash as keyword arguments

```ruby
options = { a: 4 }
default_options = { a: 2, b: 1}

def keyword_substract(a: , b:)
  a - b
end

keyword_substract(**default_options)
# => 1
# But this will fail because its missing the b: key
keyword_substract(options)

# You can merge in the default options
# Note: You have to merge options into default to override the defaults
options_with_default = default.merge(options) 

keyword_substract(options_with_default)
# => 3
```

This can be useful to providing default params or varying some params based on external conditions.
