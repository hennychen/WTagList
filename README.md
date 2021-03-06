WTagList
=========

Create a list of tags from an NSArray to show in a view with customisable fonts, colors etc.

![preview](https://raw.github.com/ashikahmad/WTagList/master/Screenshot.png "Preview")

## Set Up

1. Simple copy over `WTagList.h` and `WTagList.m` into your project.
2. Make sure you have linked the framework `QuartzCore.framework`.

## Use

### Add To View

* In code:
```obj-c
    // Initalise and set the frame of the tag list
    tagList = [[WTagList alloc] initWithFrame:CGRectMake(20.0f, 70.0f, 280.0f, 300.0f)];
    
    // Add the taglist to your UIView
    [self.view addSubview:tagList];
```
* In XIB

    1. Add a UIScrollView in your view.
    2. Change class as `WTagList`.

### Set Tags
```obj-c
    // Set the items to the array
    NSArray *array = [[NSArray alloc] initWithObjects:@"Foo", @"Tag Label 1", @"Tag Label 2", @"Tag Label 3", @"Tag Label 4", @"Tag Label 5", nil];
    [tagList setTags:array];
```
### Other Features

* Add/remove/find
```obj-c
    // Add Tags
    [taglist addTag:@"Another Tag"];
    
    // Remove Tags
    [taglist removeTagWithText:@"Another Tag"];
    
    // Find Tag
    TagView *tag = [tagList tagWithText:@"Foo"];
```
* Layout, AutoSort, Animate Changes
```obj-c
    // Default is WTagLayoutFlow, Other options: WTagLayoutHorizontal/WTagLayoutVertical
    tagList.layout = WTagLayoutHorizontal
    
    // Tags will be shown sorted, but original order in textArray will be preserved
    tagList.autoSort = YES;
    
    // Any changes that needs re-layout like sorting, adding, removing, layout-change will be animated
    tagList.animateChanges = YES
```

## Customisation

In `WTagList.m` there are a number of customisable options to change the layout and the aesthetics of the tags:

    #define CORNER_RADIUS 10.0f
    #define LABEL_MARGIN 5.0f
    #define BOTTOM_MARGIN 5.0f
    #define FONT_SIZE 13.0f
    #define HORIZONTAL_PADDING 7.0f
    #define VERTICAL_PADDING 3.0f
    #define BACKGROUND_COLOR [UIColor colorWithRed:0.93 green:0.93 blue:0.93 alpha:1.00]
    #define TEXT_COLOR [UIColor blackColor]
    #define TEXT_SHADOW_COLOR [UIColor whiteColor]
    #define TEXT_SHADOW_OFFSET CGSizeMake(0.0f, 1.0f)
    #define BORDER_COLOR [UIColor lightGrayColor].CGColor
    #define BORDER_WIDTH 1.0f
    #define DEFAULT_AUTOMATIC_RESIZE NO

NOTE: In the future, these will be added as methods that can be used to customise the tags after initialisation.

## License

I have included the license in the `LICENSE` file. I've got it as the MIT license, mainly because I want people to do what they want with this library.

If you do something cool, or find any problems, please create a pull request and I will look at including any of your changes into this project.
