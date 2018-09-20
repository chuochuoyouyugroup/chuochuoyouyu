模块设计

模块6  用户模块

（一）实现该模块的类：游客类，注册用户类，付费用户类，解答人类。
class Customer :
{
private:string id;
	public:
		void register();
		void scanning(Live* lives);
void scanning(LiveRoom* chats);
		void login(string username,string password);
}

1. 游客类
（1）类的属性
   游客类（基类）包含的属性包括用户id。
用户id：每位用户作为游客访问应用各项内容时，系统都会给该游客随机分配id，作为该用户的唯一标识。
（2）类的方法
游客类中包含注册、浏览、登录。
i)注册
游客通过调用注册函数，完成用户的注册，包括用户名，用户昵称，密码，手机等基本信息，作为登录注册用户的凭证，并把注册的信息存入数据库。
ii)浏览
游客通过调用浏览函数，可以完成浏览应用各个模块的功能，包括浏览直播列表，浏览聊天室列表，通过浏览函数，游客可以在直播列表里面选择观看直播，在聊天室列表里面选择进入聊天室内交流。
iii)登录
游客通过调用登录函数实现注册用户的登录，通过用户输入的用户名和密码与数据库中的注册用户信息进行比较，核对无误后登录成为注册用户，注册用户继承游客类的所有属性和方法。

2.注册用户类
class registerUser :public Customer
{
private:
string username;
string password;
string name;
int sex;
int age;
int language;
string phonenumber;
	public:
		void lookupInformation(registerUser const*AregisterUser);
		void changeInformation(registerUser &AregisterUser);
void buyPaid(registerUser &AregisterUser);
}

（1）类的属性
  注册用户类包含的属性包括用户名，密码，用户昵称，用户性别，用户年龄，用户倾向语言，用户手机号等。
用户名：用户通过注册登录为注册用户后，用户名为用户注册时所填的唯一标识用户名。
密码：用户通过注册登录为注册用户后，用户名为用户注册时所填的唯一标识用户名。
用户昵称：用户注册时所填的昵称。
用户性别：用户注册时所填的男/女
用户年龄：用户注册时所填的年龄。
用户倾向语言：用户注册时所填的倾向所学的语言。
用户手机号：用户注册时所填的手机号。
（2）类的方法
直播类中包含继承游客类的方法和查看和修改用户信息，购买会员。
i)查看和修改用户信息
注册用户通过调用查看和修改用户信息方法可以对用户的相关属性（用户昵称，用户性别，用户性别，用户倾向语言和用户手机号等）进行查看和修改。
ii)购买会员
注册用户通过调用购买会员函数，完成会员付费后开通会员，将注册用户在数据库中升级成为付费用户，转向付费用户类。

