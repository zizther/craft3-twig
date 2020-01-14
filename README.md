# Craft 3 CMS Package for Atom

Add snippets and template tags for the [Craft CMS](https://buildwithcraft.com/) to Twig & HTML files in Atom.

A port from [BarrelStrength Craft-Twig.tmbundle](https://github.com/BarrelStrength/Craft-Twig.tmbundle) for sublime.

### Twig Tags (via tab trigger)

    }}              {{  }}
    %%              {%  %}
    ##              {#  #}

    extends         {% extends 'template' %}
    inc             {% include 'template' with vars %}
    incp            {% include 'template' with {
                      key: 'value'
                    }} %}

    set, setb       {% set var = value %}
    block, blockb   {% block name %} ... {% endblock %}
    filter, filterb {% filter name %} ... {% endfilter %}

    if, ifb         {% if condition %} ... {% endif %}
    ife             {% if condition %} ... {% else %} ... {% endif %}
    ifeif           {% if condition %} ... {% elseif condition %} ... {% endif %}
    ifeife          {% if condition %} ... {% elseif condition %} ... {% else %} ... {% endif %}
    import          {% import 'template' as key %}
    for             {% for item in seq %} ... {% endfor %}
    fore            {% for item in seq %} ... {% else %} ... {% endfor %}
    else            {% else %}
    elseif          {% elseif condition %}

    endif           {% endif %}
    endfor          {% endfor %}
    endset          {% endset %}
    endblock        {% endblock %}
    endfilter       {% endfilter %}

### Twig Tags, Customised for Craft (via tab trigger)

    assets, assetsp          craft.assets loop
    categories, categoriesp  craft.categories loop
    entries, entriesp        craft.entries loop
    feed                     craft.feeds.getFeedItems loop
    tags, tagsp              craft.tags loop
    users, usersp            craft.users loop

    cache              {% cache %} ... {% endcache %}
    ciel               ceil()
    csrf               {{ csrfInput() }}
    exit               {% exit 404 %}
    endmacro           {% endmacro %}
    floor              floor()

    includecss         {% css %} ... {% endcss %}
    registerCssFile    {% do view.registerCssFile(/resources/css/global.css) %}
    includejs          {% js %} ... {% endjs %}
    registerJsFile     {% do view.registerJsFile(/resources/js/global.js) %}

    macro              {% macro name(param) %} ... {% endmacro %}
    matrix             Outputs a basic Matrix Field loop
    max                max()
    min                min()
    paginate           Simple:   Outputs an example of pagination with craft.entries
                       Advanced: Outputs an example of pagination with craft.entries
    redirect           {% redirect 'login' %}
    getparam           craft.app.request.getParam()
    getpost            craft.app.request.getPost()
    getquery           craft.app.request.getQuery()
    getsegment         craft.app.request.getSegment()
    requirelogin       {% requireLogin %}
    requirepermission  {% requirePermission "spendTheNight" %}
    round              num|round
    shuffle            shuffle()
    switch             {% switch variable %}{% endswitch %}
    url, urla          url('path'), url('path', params, 'http', false)
