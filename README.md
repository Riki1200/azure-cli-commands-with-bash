# AZURE CLI COMMANDS


azure

	account
		list [options]				#List the imported subscriptions
		show [options] [subscriptionNameOrId] 	#Show details about a subscription
		set [options] <subscriptionNameOrId> 	#Set the current subscription
		clear [options]				#Remove a subscription or environment, or clear all of the stored account and environment info
		import [options] <file>			#Import a publishsettings file or certificate for your account
		download [options]			#Launch a browser to download your publishsettings file
		env...					#Commands to manage your account environment
			list [options]
			show [options] [environment]
			add [options] [environment]
			set [options] [environment]
			delete [options] [environment]
		affinity-group...			#Commands to manage your Affinity Groups
			list [options]
			create [options] <name>
			show [options] <name>
			delete [options] <name>
		cert...					#Commands to manage your account certificates
			export [options]

	config
		list [options]				#List config settings
		delete [options] <name>			#Delete a config setting
		set <name> <value>			#Update a config setting
		mode [options] <name>			#Sets the cli working mode, valid names are 'arm' for resource manager and 'asm' for service management


	network
		export [options] <file-path>				#Export the current Network configuration to a file
		import [options] <file-path>				#Set the Network configuration from a json file
		dnsserver...						#Commands to manage your DNS Servers
			list [options]
			register [options] <dnsIp>
			unregister [options] <dnsIp>
		vnet...							#Commands to manage your Virtual Networks
			list [options]
			show <vnet> [options]
			delete [options] <vnet>
			create [options] <vnet>
			static-ip...					#Commands to manage your Virtual Network static IP addresses
				check [options] <vnet> <ip-address>
			reserved-ip...					#Commands to manage your reserved public Virtual IP addresses
				list [options]
				show [options] <name>
				delete [options] <name>
				create [options] <name> <location>

	sb
		namespace						#Commands to manage your Service Bus namespaces
			list [options]
			show [options] [name]
			check [options] <name>
			create [options] <namespace> <region>
			delete [options] [namespace]
			location...					#Commands to manage your Service Bus locations
				list [options]

	vm
		create [options] <dns-name> <image> [userName] [password]	#Create a VM
		create-from [options] <dns-name> <role-file>			#Create a VM from json role file
		list [options]							#List the VM
		show [options] <name>						#Show details about the VM
		delete [options] <name>						#Delete the VM
		start [options] <name>						#Start the VM
		restart [options] <name>					#Restart the VM
		shutdown [options] <name>					#Shutdown the VM
		capture [options] <vm-name> <target-image-name>			#Capture the VM as OS Image or VM Image
		export [options] <vm-name> <file-path>				#Export a VM to a file
		extension...							#Commands to manage VM resource extensions
			list [options]
			set [options] <vm-name> <extension-name> <publisher-name> <version>
			set-chef [options] <vm-name>
			get [options] <vm-name>
			get-chef [options] <vm-name>
		docker...							#Commands to manage your Docker Virtual Machine
			create [options] <dns-name> <image> <user-name> [password]
		location...							#Commands to manage your Virtual Machine locations
			list [options]
		static-ip...							#Commands to manage your Virtual Machine static IP address
			show [options] <vm-name>
			set [options] <vm-name> <ip-address>
			remove [options] <vm-name>
		public-ip...							#Commands to manage your Virtual Machine public IP address
			list [options] [vm-name]
			set [options] [vm-name] [publicip-name]
			delete [options] [vm-name] [publicip-name]
		endpoint...							#Commands to manage your Virtual Machine endpoints
			create [options] <vm-name> <lb-port> [vm-port]
			create-multiple [options] <vm-name> <lb-port>[:<vm-port>[:<protocol>[:<enable-direct-server-return>[:<lb-set-name>[:<probe-protocol>[:<probe-port>[:<probe-path>[:<internal-lb-]]]] {1-*}
			delete [options] <vm-name> <endpoint-name>
			update [options] <vm-name> <endpoint-name>
			list [options] <vm-name>
			show [options] <vm-name>
			acl-rule...						#Commands to manage your Virtual Machine endpoint's ACL rules
				reate [options] [vm-name] [endpoint-name] [order] [action] [remote-subnet]
				list [options] [vm-name] [endpoint-name]
				delete [options] [vm-name] [endpoint-name] [order]
				set [options] [vm-name] [endpoint-name] [order]
		image...							#Commands to manage your Virtual Machine images
			show [options] <name>
			list [options]
			delete [options] <name>
			create [options] <name> [source-path]
		disk...								#Commands to manage your Virtual Machine data disks
			show [options] <name>
			list [options] [vm-name]
			delete [options] <name>
			create [options] <name> [source-path]
			upload [options] <source-path> <blob-url> <storage-account-key>
			attach [options] <vm-name> <disk-image-name>
			attach-new [options] <vm-name> <size-in-gb> [blob-url]
			detach [options] <vm-name> <lun>
			update [options] <vm-name> <lun>

	service									# Commands to manage your Cloud Services
		create [options] <serviceName>
		list [options]
		show [options] <serviceName>
		delete [options] <serviceName>
		cert...								# Commands to manage your Cloud Services certificates
			list [options]
			create [options] <dns-name> <file> [password]
			delete [options] <thumbprint>
		internal-load-balancer...					# Commands to manage internal load balancers for your Cloud Service Deployment
			list [options] [serviceName]
			add [options] [serviceName] [internalLBName]
			delete [options] [serviceName] [internalLBName]
			set [options] [serviceName] [internalLBName]
	site
		TODO

	sql
		TODO

	storage
		account 									# Commands to manage your Storage accounts
			list [options]
			show [options] <name>
			create [options] <name>
			set [options] <name>
			delete [options] <name>
			keys...									# Commands to manage your Storage account keys
				list [options] <name>
				renew [options] <name>
			connectionstring...							# Commands to show your Storage connection string
				show [options] <name>
		blob 										# Commands to manage your Storage blobs
			list [options] [container] [prefix]
			show [options] [container] [blob]
			delete [options] [container] [blob]
			upload [options] [file] [container] [blob]
			download [options] [container] [blob] [destination]
			copy... 								# Commands to manage your blob copy operations
				start [options] [sourceUri] [destContainer]
				show [options] [container] [blob]
				stop [options] [container] [blob] [copyid]
			sas...									# Commands to manage shared access signature of your Storage blob
				create [options] [container] [blob] [permissions] [expiry]
		container 									# Commands to manage your Storage containers
			create [options] [container]
			show [options] [container]
			delete [options] [container]
			set [options] [container]
			sas...									# Commands to manage shared access signatures of your Storage container
				create [options] [container] [permissions] [expiry]
			policy...								# Commands to manage stored access policies of your Storage container
				create [options] [container] [name]
				show [options] [container] [name]
				list [options] [container]
				set [options] [container] [name]
				delete [options] [container] [name]
		queue 										# Commands to manage your Storage queues
			create [options] [queue]
			list [options] [prefix]
			show [options] [queue]
			delete [options] [queue]
			sas...									# Commands to manage shared access signatures of your Storage queue
				create [options] [queue] [permissions] [expiry]
			policy...								# Commands to manage stored access policies of your Storage queue
				create [options] [queue] [name]
				show [options] [queue] [name]
				list [options] [queue]
				set [options] [queue] [name]
				delete [options] [queue] [name]
		table										# Commands to manage your Storage tables
			create [options] [table]
			list [options] [prefix]
			show [options] [table]
			delete [options] [table]
			sas...									# Commands to manage shared access signatures of your Storage table
				create [options] [table] [permissions] [expiry]
			policy...								# Commands to manage stored access policies of your Storage table
				create [options] [table] [name]
				show [options] [table] [name]
				list [options] [table]
				set [options] [table] [name]
				delete [options] [table] [name]
		share 										# Commands to manage your Storage file shares
			create [options] [share]
			show [options] [share]
			delete [options] [share]
			list [options] [prefix]
		file 										# Commands to manage your Storage files
			list [options] [share] [path]
			delete [options] [share] [path]
			upload [options] [source] [share] [path]
			download [options] [share] [path] [destination]
		directory 									# Commands to manage your Storage file directory
			create [options] [share] [path]
			delete [options] [share] [path]
		logging										# Commands to manage your Storage logging properties
			show [options]
			set [options]
		metrics 									# Commands to manage your Storage metrics properties
			show [options]
			set [options]
