# GuiGeometry

There are a few good geometry gems already available for Ruby (ruby-geometry and geometry), but I need one which is focused on the needs of creating 2D graphical user interfaces.

## Installation

Add this line to your application's Gemfile:

    gem 'gui_geometry'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install gui_geometry

## Usage

Points are represented by X and Y coordinates:

Rectangles consist of two point objects. One specifies the location of the rectangle - it's top-left corner. The other specifies its size in terms of width then height.

``` ruby
require "gui_geometry"
include GuiGeometry::Tools

# create point x == y == 0
> point
 => point(0,0)

# create a point x=3, y=4
> my_point = point(3,4)
 => point(3,4)

> [my_point.x, my_point.y]
 => [3, 4]

# create a rectangle with location (top-left corner) = poiunt(4,5), width=100, height=80
> rect(4,5,100,80)
 => rect(4,5,100,80)
> my_rect = rect point(4,5), point(100,80) # alternate form
 => rect(4,5,100,80)

# create a rect with location == point(0,0), size = point(30,50) (width = 30, height = 50)
> rect point(30,50)
 => rect(0,0,30,50)

# get loc and size:
> [my_rect.loc, my_rect.size]
 => [point(4,5), point(100,80)]

# get x, y, width and height
> [my_rect.x, my_rect.y, my_rect.w, my_rect.h]
 => [4, 5, 100, 80]

# get the 4 corners:
> [my_rect.tl, my_rect.tr, my_rect.bl, my_rect.br]
 => [point(4,5), point(104,5), point(4,85), point(104,85)]

```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
