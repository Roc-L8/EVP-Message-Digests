# EVP-Message-Digests
基于Openssl可以实现大量不同的散列函数，包括流行的Category：SHA-2散列函数集（即SHA-224，SHA-256，SHA-384和SHA-512）。该项目只实现了部分，要实现其他的也非常简单。

# 程序运行截图
![image](https://github.com/Ruipeng-LI/EVP-Message-Digests/blob/master/%E6%90%9C%E7%8B%97%E6%88%AA%E5%9B%BE20190129204128.png)


# 修改消息摘要算法代码说明
unsigned char * digest = (unsigned char *)OPENSSL_malloc(EVP_MD_size(EVP_sha512()));
	unsigned int digest_len = 0;
	if ((mdctx = EVP_MD_CTX_create()) == NULL)
		EVP_MD_CTX *mdctx;

	if ((mdctx = EVP_MD_CTX_create()) == NULL)
		handleErrors();

	if (1 != EVP_DigestInit_ex(mdctx, EVP_sha512(), NULL))
		handleErrors();
    
只需要修改EVP_DigestInit_ex(mdctx, EVP_sha512(), NULL)中的EVP_sha512()。修改成其他参数就通过该算法实现消息摘要
