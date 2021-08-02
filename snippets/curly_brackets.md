# Output curly bracktes without them becoming blocks
This snippet can be used to output curly brackets ('{' and '}') without having them interpreted as a TagScript block. It can be used to put TagScript blocks inside triggers made by a tag, without the blocks already executing in the tag.
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

![](https://i.imgur.com/FykQdVG.png)

#### Example with a trigger

```
{=( ):{ }}
{=(b):{ (1)}}
{=(d):{ (2)}}

{c:ar + {user(id)}> {b}reactu:<a:ragej:760909925844647936>{d}
{b}user(mention){d} {user(name)} is AFK. Please do not not ping them.}
```

![](https://i.imgur.com/A5PHS02.png)

### Explanation

```
{=( ):{ }}
{=(b):{ (1)}}
{=(d):{ (2)}}
```
The first line creates a variable whose name is a space, whose content is `{ }`. So when you parse this variable, the first element of it is `{`, and the second element of it is `}`.
Knowing this, we simply store those parsings in their own separate variable, here named "b" and "d".
So `{=(b):{ (1)}}` actually parses the first element of the `{=( ):}` variable, effectively returning `{`. Same for the `d` variable.
The first variable could have been named anything, but a space is unlikely to be the name of a variable you have in your code, so it's convenient and unlikely to conflict with the others, but it *could* be anything else.
