# prime-num_in_c-
에라토스테네스의 체를 이용해서 c++로 소수를 구하는 알고리즘.

```c++
#include <iostream>
#include <math.h>
using namespace std;

int main(){

//	int n;
//	cin >> n; // 원하는 변수의 범위가 있을 때
	int n = 100;

	bool a[n];

	a[0] = a[1] = false; // 소수가 아닌 0, 1은 미리 거짓으로 선언

	for(int i = 2; i <= n; i++)
		a[i] = true; // 일단 모든 수 들을 참으로 선언한다.

	for(int i = 0; i < sqrt(n); i++){ // 제곱근까지만 변수를 판별하면 됨.
		if (a[i]) { // 만약 참이라면
			for (int j = i * 2; j <= n; j += i) // i의 값만큼 증가시켜서 그 값들을 거짓으로 만든다.
				a[j] = false;
		}
	}

	for(int i = 0; i <= n; i++){
		if(a[i])
			cout << i << ' '; // 만약 참이라면 그 인덱스를 출력한다.
	}

	cout << endl;
	return 0;
}








```

