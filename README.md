import com.cloudbees.hudson.plugins.folder.Folder
import com.cloudbees.plugins.credentials.CredentialsProvider
import com.cloudbees.plugins.credentials.domains.Domain

def folder = Jenkins.instance.getItemByFullName("OCI-POC/OCI-CCP")
if (folder instanceof Folder) {
    def domains = CredentialsProvider.lookupDomains(folder)
    domains.each { domain ->
        println "Domain: ${domain.name}"
        println "Create URL: ${folder.getUrl()}credentials/domain/${domain.name}/createCredentials"
    }
} else {
    println "Folder OCI-POC/OCI-CCP not found"
}
