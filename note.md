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

### 身份验证【24页】

