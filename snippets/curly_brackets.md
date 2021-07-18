# Output curly bracktes without them becoming blocks
This snippet can be used to output curly brackets ('{' and '}') without having them interpreted as a TagScript block. This can be used to put TagScript blocks inside triggers made by a tag, without the blocks already executing in the tag.
```
{=( ):{ }}
{=(b):{ (1)}}
{=(d):{ (2)}}
```
After this, every `{b}` will be a '{' and every `{d}` a '}'.

#### Example

```
{=( ):{ }}
{=(b):{ (1)}}
{=(d):{ (2)}}

This tag has no {b}delete{d} block.
```

![](https://i.imgur.com/iR6HkcB.png)

This can be very useful when you want to create a trigger with a tag and you want to use TagScript blocks in the trigger.

```
{=( ):{ }}
{=(b):{ (1)}}
{=(d):{ (2)}}

{c:ar + {user(id)}> {b}reactu:<a:ragej:760909925844647936>{d}
{b}user(mention){d} {user(name)} is AFK. Please do not not ping them.}
```

![](https://i.imgur.com/RPknUiV.png)

### Explanation

When a variable is not defined before it's called, it just returns the block it self, which include the brackets([example](https://i.imgur.com/mxZiGfn.png)). Now you can parse to just get the brackets, which is easier done when using a space(red-underlined). The blue underlined space is a space because it's a simple variable name that probably isn't really used and because an empty variable name could interfere with `{=():}`.  

![](https://i.imgur.com/jb5jK1Q.png)
