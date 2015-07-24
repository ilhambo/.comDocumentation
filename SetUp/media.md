#Media
We'll cover the optional use of Azure Blob Storage for your media and why you may want or need to consider this.  In general, you can use Umbraco media with the default configuration for your sites.  If you have many images, your images are very large in size, or you store large video files as part of your site you'll want to consider using the Azure Blob Storage provider for Umbraco.

[More information](https://our.umbraco.org/projects/backoffice-extensions/azure-blob-storage-provider) 	

##Media and Git, not too much love
Git is really good at handling many versions of text-based content,  I.e. code, markdown, etc....  What git is not as good at is handling binary content, especially many versions of a particular binary file or a large binary file.  The fact that umbraco.com uses git as the file system (as do other Azure solutions) introduces a potential issue.  In addition, as umbraco.com deployments are done using a web connection, large media deployments could be slow and are subject to timeouts and other restrictions.

If this sounds like you, you should evaluate the Azure Blob Storage provider.  It is relatively simple to setup, has very few limitations and can result in better site performance as well as faster media loading times - especially if your media takes advantage of an Azure, or other, CDN.

##Setup
You can find details on how to setup and configure the Azure Blob Storage provider [here](https://our.umbraco.org/projects/backoffice-extensions/azure-blob-storage-provider).

At the time this documentation was updated (July 2015) there are a few items to be aware of when considering using this provider.

- You will need to create your own Azure Storage container or contact us if you are on an Enterprise plan that may include this
- You can not mix this provider with the default provider
- This provider works **really** well with [ImageProcessor.Web plugin for Azure cache]
(http://imageprocessor.org/imageprocessor-web/plugins/azure-blob-cache/)
- The CropUp package does not work properly with this provider
- Copy of document types with an upload field as a property will not work.


