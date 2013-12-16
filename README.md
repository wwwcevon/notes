#LABEL design

##13.12.16

###在new界面添加label的输入框

####modify new.py in views/issues

add in line 22
'''
label   = TextField(u'label', validators=[Length(min=1,
					message=u'label should not be empty')])
'''

add in line 35
'''
form.label.data
'''

#####modify issues.py in models

add in line 35
'''
label     = Column(String(255))
'''

add in line 52 70 72
'''
 label
'''

add in line 57
'''
self.label     = label
'''

####modify new.html in templates/issues

add in line 16
'''
  {{ form.new.label }} {{ form.label() }} <span class="help-inline">*</span>
  {{ error(form.errors['label']) }}
'''

####modify update.py in api/issues

add in line 20
'''
    label   = request.form.get('title', '')
'''
