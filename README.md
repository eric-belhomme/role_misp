# role_misp

Install MISP 2.4 on EL9 instance

## Requirements

A TLS certificate shall be provided, otherwise a self-signed certificate will be generated. 

## Role Variables
| MISP parameter | default | description |
|--- |--- |--- |
| misp_sql_dbname     | misp | MariaDB database name |
| misp_sql_user       | mispadmin | MariaDB user name |
| misp_sql_passwd     | _unset_ | MariaDB user password |
| misp_gpg_passphrase | _unset_ | GPG passphrase |
| misp_gpg_name       | _unset_ | GPG identity name |
| misp_gpg_email      | _unset_ | GPG email address |
| misp_tls_cert       | /etc/pki/tls/certs/misp.crt | www TLS public certificate location |
| misp_tls_key        | /etc/pki/tls/private/misp.key | www private key location |
| misp_tls_cachain    | _unset_ | TLS CA chain location |
| misp_proxy_host   | '' | The hostname of an HTTP proxy for outgoing sync requests. Leave empty to not use a proxy. |
| misp_proxy_port   | '' | The TCP port for the HTTP proxy.	This setting has to be a number. |
| misp_proxy_method | '' | The authentication method for the HTTP proxy. Currently supported are Basic or Digest. Leave empty for no proxy authentication |
| misp_proxy_user   | '' | The authentication username for the HTTP proxy |
| misp_proxy_passwd | '' | The authentication password for the HTTP proxy |
| misp_base_url | `https://{{ ansible_fqdn }}` | The base url of the application (in the format https://www.mymispinstance.com or https://myserver.com/misp). Several features depend on this setting being correctly set to function. |
| misp_external_base_url | `misp_base_url` | The base url of the application (in the format https://www.mymispinstance.com) as visible externally/by other MISPs. MISP will encode this URL in sharing groups when including itself. If this value is not set, the baseurl is used as a fallback |
| misp_email_from_name | MISP | Notification e-mail sender name. |
| misp_cortex_host | The url used to access Cortex. By default, it is accessible at http://cortex-url| 
| misp_cortex_port | 9000 | The port used to access Cortex. By default, this is port 9000 |

## License

BSD

## Author Information
SCC France - Eric Belhomme <ebelhomme@fr.scc.com>
