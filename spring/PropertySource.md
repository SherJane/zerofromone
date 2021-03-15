`@Configuration  
@PropertySource(value = "classpath:resources.properties", ignoreResourceNotFound = false)  `

PropertyPlaceholderHelper解析嵌套占位符

`@PropertySource(value = "classpath:${env}/resources.properties")`

