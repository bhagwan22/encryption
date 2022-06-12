## classic encryption: 
```
free in sf(with we can protect specific type of custom text field by 128-bit AES) and Only users with the View Encrypted Data permission can see data in encrypted custom text fields.
 https://developer.salesforce.com/docs/atlas.en-us.232.0.securityImplGuide.meta/securityImplGuide/fields_about_encrypted_fields.htm
```

# Shield Platform Encryption
- free in developer org but need to purchase licence for other org


- shield platform encryption data at rest(mean any data that’s inactive or stored in files, spreadsheets, standard and custom fields, and even databases and data warehouse) with 256 bit AES key
- shield platform give advantage to prove compliance

- Keys and secrets work together to provide layers of security. 
	- key - sting(use to scremble/unscremble data)
	- Secrets : pieces of keys(use to secure keys)
		- Tenant secrets and master secrets are keys for keys 
		- If hackers get your key, they also must navigate the secret decryption process controlled by the master and tenant secrets before they can use your key.
			- sf generate 3 master secret per yr with each new release
			- Your tenant secret partners with the master secret in what’s called a key derivation process to create keys that encrypt and decrypt your data.
			- person can update it's tanent secret as many time he wants

Note: Unlike passwords, you can’t reset a tenant secret. Salesforce can’t help with deleted, destroyed, or misplaced tenant secrets. Always back up tenant secrets.

### SETUP:
- permission set: enable the Customize Application and Manage Encryption Keys permissions
- setup -> platform encryption --> key Management -> Generate Tanent secret
- setup -> paltform encryption --> Encryption policy --> select one of type
Note:  Field values are encrypted only in records created or updated after encryption is enabled.

