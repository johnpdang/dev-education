---
description: A grid system based on the flex display property.
---

# Flexbox grid

{% embed url="http://flexboxgrid.com/" %}



### Responsive

Responsive modifiers enable specifying different column sizes, offsets, alignment and distribution at xs, sm, md & lg viewport widths.

```text
<div class="row">
    <div class="col-xs-12
                col-sm-8
                col-md-6
                col-lg-4">
        <div class="box">Responsive</div>
    </div>
</div>
```

### Fluid

Percent based widths allow fluid resizing of columns and rows.

```text
.col-xs-6 {
  flex-basis: 50%;
}
```

### Simple Syntax

All you need to remember is row, column, content.

```text
<div class="row">
    <div class="col-xs-12">
        <div class="box">12</div>
    </div>
</div>
```

### Offsets

Offset a column

```text
<div class="row">
    <div class="col-xs-offset-3 col-xs-9">
        <div class="box">offset</div>
    </div>
</div>
```

### Auto Width

Add any number of auto sizing columns to a row. Let the grid figure it out.

```text
<div class="row">
    <div class="col-xs">
        <div class="box">auto</div>
    </div>
</div>
```

### Nested Grids

Nest grids inside grids inside grids.

```text
<div class="row">
    <div class="col-xs">
        <div class="box">
            <div class="row">
                <div class="col-xs">
                    <div class="box">auto</div>
                </div>
            </div>
        </div>
    </div>
</div>
```

### Alignment

Add classes to align elements to the start or end of a row as well as the top, bottom, or center of a column

#### `.start-`

```text
<div class="row start-xs">
    <div class="col-xs-6">
        <div class="box">
            start
        </div>
    </div>
</div>
```

#### `.center-`

```text
<div class="row center-xs">
    <div class="col-xs-6">
        <div class="box">
            start
        </div>
    </div>
</div>
```

#### `.end-`

```text
<div class="row end-xs">
    <div class="col-xs-6">
        <div class="box">
            end
        </div>
    </div>
</div>
```

Here is an example of using the modifiers in conjunction to acheive different alignment at different viewport sizes.Example

```text
<div class="row center-xs end-sm start-lg">
    <div class="col-xs-6">
        <div class="box">
            All together now
        </div>
    </div>
</div>
```

#### `.top-`

```text
<div class="row top-xs">
    <div class="col-xs-6">
        <div class="box">
            top
        </div>
    </div>
</div>
```

#### `.middle-`

```text
<div class="row middle-xs">
    <div class="col-xs-6">
        <div class="box">
            center
        </div>
    </div>
</div>
```

#### `.bottom-`

```text
<div class="row bottom-xs">
    <div class="col-xs-6">
        <div class="box">
            bottom
        </div>
    </div>
</div>
```

### Distribution

Add classes to distribute the contents of a row or column.

#### `.around-`

```text
<div class="row around-xs">
    <div class="col-xs-2">
        <div class="box">
            around
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            around
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            around
        </div>
    </div>
</div>
```

#### `.between-`

```text
<div class="row between-xs">
    <div class="col-xs-2">
        <div class="box">
            between
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            between
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            between
        </div>
    </div>
</div>
```

### Reordering

Add classes to reorder columns.

#### `.first-`

123456

```text
<div class="row">
    <div class="col-xs-2">
        <div class="box">
            1
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            2
        </div>
    </div>
    <div class="col-xs-2 first-xs">
        <div class="box">
            3
        </div>
    </div>
</div>
```

#### `.last-`

123456

```text
<div class="row">
    <div class="col-xs-2 last-xs">
        <div class="box">
            1
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            2
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            3
        </div>
    </div>
</div>
```

### Reversing

#### `.reverse`

123456

```text
<div class="row reverse">
    <div class="col-xs-2">
        <div class="box">
            1
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            2
        </div>
    </div>
    <div class="col-xs-2">
        <div class="box">
            3
        </div>
    </div>
</div>
```

