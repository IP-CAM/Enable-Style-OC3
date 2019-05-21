# Enable-Style-OC3

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

From catalog/view/theme/default/template/common/header.twig I would like to access the config_boxed variable.
Where and what should I add more.

```
{% if config_boxed %}
	<b>Enabled</b>
	<link href="catalog/view/theme/default/stylesheet/own.css" rel="stylesheet">
{% else %}
	 False
{% endif %}
```
Many thanks 