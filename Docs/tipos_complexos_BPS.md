# Tipos Complexos BPS - <i>Add new type to BPMN/BPS</i>

## 1st part - allows the use of the new created type in the forms without errors

1. Create new maven project

2. Add this dependency to pom.xml

   ```xml
   <dependency>
   	<groupId>org.activiti</groupId>
   	<artifactId>activiti-engine</artifactId>
   	<version>5.22.0</version>
   </dependency>
   ```

3. Create a new class, e.g. TableFormType (this class should extend “AbstractFormType”)

   ```java
   public class TableFormType extends AbstractFormType {
   	public static final String TYPE_NAME = "table";
   
   	public String getName() {
   		return TYPE_NAME;
   	}
   
   	@Override
   	public Object convertFormValueToModelValue(String propertyValue) {
   		Integer table = Integer.valueOf(propertyValue);
   		return table;
   	}
   
   	@Override
   	public String convertModelValueToFormValue(Object modelValue) {
   		if	(modelValue	== null) {
   			return null;
   		}
   		return modelValue.toString();
   	}
   }
   ```

4. Run maven install.

5. Copy the generated jar to.

   ```
   WSO2\Enterprise Integrator\6.4.0\lib\
   ```

6. Add this to activiti.xml

   ```xml
   <bean id="processEngineConfiguration" ... >
       ...
       <property name="customFormTypes">
           <list>
               <bean class="bpmn.custom.type.table.TableFormType"/>
           </list>
       </property>
   </bean>
   ```

7. Restart BPS.

## 2nd part - allows the rendering of the new type

1. Find **dynamicFormGen.js**

   ```
   6.4.0\wso2\business-process\repository\deployment\server\jaggeryapps\bpmn-explorer\assets
   ```

2. Find the function **generateForm(data, disabled)**

3. Add this to the end of it

   ```javascript
   function generateForm(data, disabled) {
   	var	formContent	=	"";
   	for	(var i = 0; i < data.length; i++) {
   		...
   		...
   		else if	(data[i].type == "table") {
   			formContent	+= genSelection(data[i], disabled);
   		}
   	}
   	return	formContent;
   }
   ```

4. Create genTable function:

   ```javascript
   functio genSelection(data,	disabled)	{
   	var dataInfo = JSON.parse(data.value);
   	var	content	= "<div class='small-med'>";
   	// here goes the logic to create and fill the table
      // e.g.
      content += '<select name="preferencia">';
      content += '<option value="op1">Opcao 1</option>';
      content += '<option value="op2">Opcao 2</option>';
      content += '</select>'

   	content	+= "</div>";
   	return	content;
   }
   ```

5. Find **action.js**

   ```
   6.4.0\wso2\business-process\repository\deployment\server\jaggeryapps\bpmn-explorer\js
   ```

6. Find the function **completeTask(data, id)**

7. Add this 

   ```javascript
   ...
   } else if	(vData[j].type === "enum") {
   	variables.push({
   		"name" : data[i].name,
   		"value" : data[i].value,
   	});
   } else if (vData[j].type === "table") {
   	variables.push({
   		"name" : data[i].name,
   		"value"	: data[i].value,
   	});
   } else {
   ...
   ```

8. Restart BPS