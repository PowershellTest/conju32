@Grab('org.yaml:snakeyaml:1.17')
import org.yaml.snakeyaml.Yaml
import hudson.model.*

node {
stage ("Start"){
    try{
    Yaml parser = new Yaml()
    def datas = parser.load(("input.yml" as File).text)
    if(datas.get("jenkins").getAt("job_type").equals("Maven"))
	{
	maven{}
	}
	else if (datas.get("jenkins").getAt("job_type").equals("Gradle"))
	{
	gradle{}
	}
}
catch(Exception e)
{
     e.printStackTrace()
}
    stage ("End"){
        echo "Last"
    }
  }
}