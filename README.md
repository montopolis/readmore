# Text Read More


Works by adding a macro to Laravel Nova `Text` which is extended by `TextArea` so it works for both.

### Install

```$xslt
composer require mattsplat/readmore
```

### Usage with TextArea

```$xslt
Textarea::make('Notes')
    ->onlyOnIndex()
    ->readMore()
    ->nullable()
// Textarea will not show on 
Textarea::make('Notes')
                
```

with options

```$xslt
Textarea::make('Notes')->nullable(),
Textarea::make('Notes')
                ->onlyOnIndex()
                ->readMore(['mask' => 'Look Here', 'max' => 5]),
```

or

```$xslt

Text::make('Notes')->readMore(),

```


#### Options
- max - number of characters to display
- mask - text displayed to show all text (this accepts raw html as well)


Use an icon instead of text 

```$xslt
$icon = '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M6 2h9a1 1 0 0 1 .7.3l4 4a1 1 0 0 1 .3.7v13a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V4c0-1.1.9-2 2-2zm9 2.41V7h2.59L15 4.41zM18 9h-3a2 2 0 0 1-2-2V4H6v16h12V9zm-5 4h2a1 1 0 0 1 0 2h-2v2a1 1 0 0 1-2 0v-2H9a1 1 0 0 1 0-2h2v-2a1 1 0 0 1 2 0v2z"/></svg>';

Text::make('Notes')->readMore(['max' => 0, 'mask' => $icon]),
```
