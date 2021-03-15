 Spring宽松绑定规则(relaxed binding)



@ConfigurationPropertiesBinding

`@Component
@ConfigurationPropertiesBinding
public class WeightConverter implements Converter<String, Weight>{

	@Override
	public Weight convert(String source) {
		int length = source.length();
		StringBuilder numBuilder = new StringBuilder();
		for(int i = 0;i <length;i++) {
			if(StringUtils.isNumeric(source.substring(i, i))) {
				numBuilder.append(source.substring(i, i));
			}else {
				break;
			}
		}
		
		return new Weight(Integer.parseInt(numBuilder.toString()), WeightUnit.parse(source.substring(numBuilder.length())));
	}

}`