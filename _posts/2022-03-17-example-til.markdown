---
layout: post
title:  "Ruby splat operator"
date:   2022-03-17 09:33:15 +0100
categories: til random ruby
---

# Ruby splat `*` and double splat `**` operator

You can use splat operator to 'unwrap' array as separate arguments
```ruby
numbers = [1, 3, 5]

def sum(*number)
  
end

```

You can use double splat operator `**` to unwrap hash as keyword arguments

This can be useful to providing default params or varying some params based on external conditions
