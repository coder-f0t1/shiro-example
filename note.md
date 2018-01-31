#### Shiro ini配置

[main]

配置应用程序的SecurityManager实例及任何它的依赖组件的地方

例如：

[main]

sha256Matcher = org.apache.shiro.authc.credential.Sha256CredentialsMatcher

myRealm = com.company.security.shiro.DatabaseRealm

myRealm = connectionTimeout = 30000

myRealm.username = jsmith

myRealm.password = secret

myRealm.credentialsMatcher = $sha256Matcher



[users]

[users]section允许你定义一组静态的用户账户，这在大部分拥有少数用户账户或用户账户不需要在运行时被动态地创建的环境下是很有用的。

[users]

admin=secret

lonestarr = vespa, goodguy, schwartz

darkhelmet = ludicrousspeed, badguy, schwartz



#### 格式：

* username = password,roleName1,roleName2,...,roleNameN
* 密码是必须的，角色是可选的。

[roles]

[roles]section 允许爸定义在[users]section中的角色与权限关联起来。另外，这在大部分拥有少数账户或用户账户不需要在运行时被动态的创建的环境地下是很有用的。

[roles]

admin=*

schwartz = lightsaber"*

goodguy = winnebago:drive:eagle5

### 身份验证(Authentication)

* Principals(身份)是subject的'identifying attributes(标识属性)'principals可以使任何能够证明subject的东西，但最好还是唯一的
* Credentials(凭证)通常是只能被subject知道的秘密，作为一种起支持作用的证据，比如：密码、指纹、视网膜信息及证书等
* principals/credential配对最常见的例子是用户名和密码。

Authenticating Subject(验证Subjects)

* 验证Subjects的过程，可以分解为三个不同的步骤：

  1.收集subjects提交的Principals(身份)和Credentials(凭证)：

  ​	UsernamePasswordToken token = new UsernamePasswordToken(username,password);

  ​	token.setRememberMe(true);

  2.提交Principals和credentials进行验证；

  3.如果提交成功，则允许访问，否则重新进行身份验证或者阻止访问。

### 授权(Authorization)

### Apache Shiro Realms

* Realm是一个能够访问应用程序特定的安全数据（如用户、角色及权限）的组件

【49页】