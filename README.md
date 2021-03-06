# Before adding a new SSH key to your account on {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %}, you should have:

Checked for existing SSH keys
Generating a new SSH key and adding it to the ssh-agent
After adding a new SSH key to your account on {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %}, you can reconfigure any local repositories to use SSH. For more information, see "Switching remote URLs from HTTPS to SSH."

{% data reusables.ssh.key-type-support %}

{% mac %}

{% include tool-switcher %} {% webui %}

Copy the SSH public key to your clipboard.
If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

$ pbcopy &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
# Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard

{% tip %}

Tip: If pbcopy isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.

{% endtip %}

{% data reusables.user_settings.access_settings %} {% data reusables.user_settings.ssh %} 4. Click New SSH key or Add SSH key.  5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air". 6. Paste your key into the "Key" field.  7. Click Add SSH key.  {% data reusables.user_settings.sudo-mode-popup %}

{% endwebui %}

{% endmac %}

{% windows %}

{% include tool-switcher %}

{% webui %}

Copy the SSH public key to your clipboard.
If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

$ clip &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
# Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard

{% tip %}

Tip: If clip isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.

{% endtip %}

{% data reusables.user_settings.access_settings %} {% data reusables.user_settings.ssh %} 4. Click New SSH key or Add SSH key.  5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air". 6. Paste your key into the "Key" field.  7. Click Add SSH key.  8. If prompted, confirm your {% data variables.product.product_name %} password. 

{% endwebui %}

{% endwindows %}

{% linux %}

{% include tool-switcher %} {% webui %}

Copy the SSH public key to your clipboard.
If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

$ cat ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
# Then select and copy the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file
# displayed in the terminal to your clipboard

{% tip %}

Tip: Alternatively, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.

{% endtip %}

{% data reusables.user_settings.access_settings %} {% data reusables.user_settings.ssh %} 4. Click New SSH key or Add SSH key.  5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air". 6. Paste your key into the "Key" field.  7. Click Add SSH key.  8. If prompted, confirm your {% data variables.product.product_name %} password. 

{% endwebui %}

{% endlinux %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

Before you can use the {% data variables.product.prodname_cli %} to add an SSH key to your account, you must authenticate to the {% data variables.product.prodname_cli %}. For more information, see gh auth login in the {% data variables.product.prodname_cli %} documentation.

To add an SSH key to your GitHub account, use the ssh-key add subcommand, specifying your public key.

gh ssh-key add <em>key-file</em>

To include a title for the new key, use the -t or --title flag.

gh ssh-key add <em>key-file</em> --title "personal laptop"

If you generated your SSH key by following the instructions in "Generating a new SSH key", you can add the key to your account with this command.

gh ssh-key add ~/.ssh/id_ed25519.pub

{% endcli %}

{% ifversion fpt or ghec %}

Further reading"Authorizing an SSH key for use with SAML single sign-on" {% endif %}
