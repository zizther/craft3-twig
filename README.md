# Craft 3 CMS Package for Atom

Add snippets and template tags for the [Craft CMS](https://craftcms.com/) to Twig & HTML files in Atom.

A port from [BarrelStrength Craft-Twig.tmbundle](https://github.com/BarrelStrength/Craft-Twig.tmbundle) for sublime.

### Twig Tags (via tab trigger)

    }}              {{  }}
    %%              {%  %}
    ##              {#  #}

    extends         {% extends 'template' %}
    import          {% import 'template' as key %}
    inc             {% include 'template' %}
    incp            {% include 'template' with {
                        key: 'value'
                    }} %}

    set             {% set var = value %}
    setb            {% set var %} ... {% endset %}
    block           {% block name %} ... {% endblock %}
    filter          {% filter name %} ... {% endfilter %}

    if, ifb         {% if condition %} ... {% endif %}
    ife             {% if condition %} ... {% else %} ... {% endif %}
    ifeif           {% if condition %} ... {% elseif condition %} ... {% endif %}
    ifeife          {% if condition %} ... {% elseif condition %} ... {% else %} ... {% endif %}
    else            {% else %}
    elseif          {% elseif condition %}
    for             {% for item in seq %} ... {% endfor %}
    fore            {% for item in seq %} ... {% else %} ... {% endfor %}

    endif           {% endif %}
    endfor          {% endfor %}
    endset          {% endset %}
    endblock        {% endblock %}
    endfilter       {% endfilter %}
    endmacro        {% endmacro %}

### Twig Tags, Customised for Craft (via tab trigger)

    assets             craft.assets loop
    categories         craft.categories loop
    entries            craft.entries loop
    feed               craft.feeds.getFeedItems loop
    tags               craft.tags loop
    users              craft.users loop

    cache              {% cache %} ... {% endcache %}
    cacheg             {% cache globally %} ... {% endcache %}
    cachek             {% cache with key %} ... {% endcache %}
    cachegk            {% cache globally with key %} ... {% endcache %}
    cachef             {% cache for condition %} ... {% endcache %}
    cacheuntil         {% cache until condition %} ... {% endcache %}
    cacheunless        {% cache unless condition %} ... {% endcache %}

    csrf               {{ csrfInput() }}
    exit               {% exit 404 %}
    dd                 {% dd output %}

    includecss         {% css %} ... {% endcss %}
    registerCssFile    {% do view.registerCssFile(/resources/css/global.css) %}
    includejs          {% js %} ... {% endjs %}
    registerJsFile     {% do view.registerJsFile(/resources/js/global.js) %}

    macro              {% macro name(param) %} ... {% endmacro %}
    matrix             Outputs a basic Matrix Field loop
    paginatesimple     Simple:   Outputs an example of pagination with craft.entries
    paginateadvanced   Advanced: Outputs an example of pagination
    redirect           {% redirect 'login' %}

    getparam           craft.app.request.getParam()
    getpost            craft.app.request.getPost()
    getquery           craft.app.request.getQuery()
    getsegment         craft.app.request.getSegment()

    requirelogin       {% requireLogin %}
    requirepermission  {% requirePermission "spendTheNight" %}

    switch             {% switch variable %}{% endswitch %}
    shuffle            shuffle()
    url, urla          url('path'), url('path', params, 'http', false)

    ciel               ceil()
    floor              floor()
    max                max()
    min                min()
    round              num|round

    info               info: site
    infoapp            info: craft.app.request
    infoassets         info: craft.assets
    infocategories     info: craft.categories
    infoconfig         info: config
    infoentries        info: craft.entries
    infofeeds          info: feeds
    infofields         info: fields
    infoglobals        info: globals
    infosections       info: sections
    infosessions       info: sessions
    infotags           info: tags
    infousers          info: users
