# Enable-Style-OC3
# Adding new style Enable/Disable option button in Opencart 3.0.3.2 admin page.


I added in admin/controller/setting/setting.php

```
if (isset($this->request->post['config_boxed'])) {
			$data['config_boxed'] = $this->request->post['config_boxed'];
		} else {
			$data['config_boxed'] = $this->config->get('config_boxed');
}
```

in admin/view/template/setting/setting.twig the following code

```
<div class="form-group">
        <label class="col-sm-2 control-label" for="input-boxed">Doboz</label>
        <div class="col-sm-10">
        <select name="config_boxed" id="input-boxed" class="form-control">
            {% if config_boxed %}
            <option value="1" selected="selected">Enabled</option>
            <option value="0">Disabled</option>
            {% else %}
            <option value="1">Enabled</option>
            <option value="0" selected="selected">Disabled</option>
            {% endif %}
        </select>
        </div>
</div> 
```

in catalog/controller/common/header.php in the end

```
	$data['config_boxed'] = $this->config->get('config_boxed');
```

in catalog/view/theme/default/template/common/header.twig 

```
{% if config_boxed %} 
	<link href="catalog/view/theme/kedvenc/stylesheet/new.css" rel="stylesheet">
{% else %} 
	<link href="catalog/view/theme/kedvenc/stylesheet/old.css" rel="stylesheet">
{% endif %}
```

Done!