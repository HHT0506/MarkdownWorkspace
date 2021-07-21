服务器端

```cpp
#include<boost/asio/ip/tcp.hpp>

#include<iostream>
using namespace std;
using namespace boost::asio;
int main()
{
	try {
		typedef ip::tcp::acceptor acceptor_type;
		typedef ip::tcp::endpoint endpoint_type;
		typedef ip::tcp::socket socket_type;
		cout << "server start." << endl;
		io_service io;

		acceptor_type acceptor(io, endpoint_type(ip::tcp::v4(), 6688));
		cout << acceptor.local_endpoint().address() << endl;

		for (;;)
		{
			socket_type sock(io);
			acceptor.accept(sock);

			cout << "client:";
			cout << sock.remote_endpoint().address() << endl;
			sock.send(buffer("hello asio"));

		}


	}
	catch (exception &e)
	{
		cout << e.what() << endl;
	}
}
```



客户端

```cpp
#include<boost/asio/ip/tcp.hpp>

#include<iostream>
#include<vector>
using namespace std;
using namespace boost::asio;

int main()
{
	try {

		typedef ip::tcp::endpoint endpoint_type;
		typedef ip::tcp::socket socket_type;
		typedef ip::address address_type;

		cout << "client start." << endl;
		io_service io;
		socket_type sock(io);
		endpoint_type ep(address_type::from_string("127.0.0.1"), 6688);

		sock.connect(ep);
		cout << sock.available() << endl;//这里应该是接收到的字节数，但输出总为0

		vector<char> str(100, 0);


		sock.receive(buffer(str));


		cout << "receive from " << sock.remote_endpoint().address() << endl;
		cout << &str[0] << endl;



	}
	catch (exception &e)
	{
		cout << e.what() << endl;
	}
	system("pause");
		
}
```



项目工程都需添加`libboost_system-vc140-mt-gd-1_64.lib`

