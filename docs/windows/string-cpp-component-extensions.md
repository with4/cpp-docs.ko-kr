---
title: "문자열 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- string support with /clr
- /clr compiler option [C++], string support
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e988da5393e32871794a2a1e7565801b0b338c2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="string--c-component-extensions"></a>문자열(C++ 구성 요소 확장)
Visual c + + 컴파일러에서는 *문자열*, 하는 일련의 문자로 텍스트를 나타내는 개체입니다. Visual c + + 문자열 값이 암시적, 변수와 값은 명시적 따옴표 붙은 문자열 리터럴을 지원 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 Windows 런타임 및 공용 언어 런타임 할당 된 메모리를 자동으로 관리 되는 개체로 문자열을 나타냅니다. 즉, 되는 문자열 변수 범위를 벗어난 또는 응용 프로그램이 종료 될 때 명시적으로 문자열에 대 한 메모리를 취소 필요가 없습니다. String 개체의 수명을 자동으로 관리 하도록 임을 나타내려면를 사용 하 여 문자열 형식 선언에서 [핸들 개체 (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) 한정자입니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 Windows 런타임 아키텍처에서는 Visual c + + 구현 하는 `String` 데이터 형식에 `Platform` 네임 스페이스입니다. 사용자 편의 위해 Visual c + + 제공는 `string` 데이터 형식, 변수인에 대 한 동의어 `Platform::String`에 `default` 네임 스페이스입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### <a name="remarks"></a>설명  
 자세한 내용과 예제 문자열에 대 한 참조 [platform:: string, std:: wstring, 및 리터럴 (플랫폼)](http://msdn.microsoft.com/en-us/ec92fbc6-edf3-4137-a85e-8e29bdb857a8)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 이 항목에서는 사용 하 여 실행 하면 Visual c + + 컴파일러에서 문자열 리터럴을 처리 하는 방법을 설명는 **/clr** 컴파일러 옵션입니다. 사용 하도록 **/clr**, 공용 언어 런타임 (CLR), C +을 사용 해야 + /CLI 구문 및 관리 되는 개체입니다. 에 대 한 자세한 내용은 **/clr**, 참조 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 로 컴파일할 때 **/clr**, 컴파일러는 문자열 리터럴 형식의 문자열로 변환 <xref:System.String>합니다. 유지 하기 위해 기존 코드를 있는 함께 이전 버전과 호환성은이 두 가지 예외가:  
  
-   예외 처리 합니다. 문자열 리터럴을 throw 되 면 컴파일러 문자열 리터럴로 catch 됩니다.  
  
-   템플릿 추론 합니다. 문자열 리터럴에 템플릿 인수로 전달 되는 경우 컴파일러는 하지 변환에 <xref:System.String>합니다. 제네릭 인수로 전달 된 문자열 리터럴으로 승격 된다는 점에 유의 <xref:System.String>합니다.  
  
 컴파일러는 해당 동작을 사용자 지정 하기 위해 재정의할 수 있는 세 명의 연산자에 대 한 기본 제공 지원도 있습니다.  
  
-   System:: string ^ 연산자 + (system:: string, system:: string);  
  
-   System:: string ^ 연산자 + (system:: object, system:: string);  
  
-   System:: string ^ 연산자 + (system:: string, system:: object);  
  
 전달 될 때는 <xref:System.String>는 컴파일러에서 필요에 따라 상자 하 고 다음 문자열 사용 (ToString)을 사용 하 여 개체를 연결 합니다.  
  
> [!NOTE]
>  캐럿 ("^") 선언 된 변수는 C +에 대 한 핸들 임을 나타냅니다 + CLI 관리 되는 개체입니다.  
  
 자세한 내용은 참조 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 결합 하 고, 문자열 비교를 보여 줍니다.  
  
```cpp  
// string_operators.cpp  
// compile with: /clr  
// In the following code, the caret ("^") indicates that the   
// declared variable is a handle to a C++/CLI managed object.  
using namespace System;  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   // variables of System::String returning a System::String  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   // accessing a character in the string  
   Console::WriteLine(a[2]);  
  
   // concatenation of three System::Strings  
   Console::WriteLine(a + b + c);  
  
   // concatenation of a System::String and string literal  
   Console::WriteLine(a + "zzz");  
  
   // you can append to a System::String ^  
   Console::WriteLine(a + 1);  
   Console::WriteLine(a + 'a');  
   Console::WriteLine(a + 3.1);  
  
   // test System::String ^ for equality  
   a += b;  
   Console::WriteLine(a);  
   a = b;  
   if (a == b)  
      Console::WriteLine("a and b are equal");  
  
   a = "abc";  
   if (a != b)  
      Console::WriteLine("a and b are not equal");  
  
   // System:String ^ and tracking reference  
   String^% rstr1 = a;  
   Console::WriteLine(rstr1);  
  
   // testing an empty System::String ^  
   String ^ n;  
   if (n == nullptr)  
      Console::WriteLine("n is empty");  
}  
```  
  
 **출력**  
  
```Output  
abcdef  
  
abcghi  
  
ghiabc  
  
c  
  
abcdefghi  
  
abczzz  
  
abc1  
  
abc97  
  
abc3.1  
  
abcdef  
  
a and b are equal  
  
a and b are not equal  
  
abc  
  
n is empty  
```  
  
 **예제**  
  
 다음 샘플은 컴파일러에서 제공 하는 연산자를 오버 로드할 수 있습니다 및 컴파일러에서는 기반으로 하는 함수 오버 로드를 찾을 <xref:System.String> 유형입니다.  
  
```cpp  
// string_operators_2.cpp  
// compile with: /clr  
using namespace System;  
  
// a string^ overload will be favored when calling with a String  
void Test_Overload(const char * a) {   
   Console::WriteLine("const char * a");   
}  
void Test_Overload(String ^ a) {   
   Console::WriteLine("String ^ a");   
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, String ^ b) {  
   return ("overloaded +(String ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(Object ^ a, String ^ b) {  
   return ("overloaded +(Object ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, Object ^ b) {  
   return ("overloaded +(String ^ a, Object ^ b)");  
}  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   Test_Overload("hello");  
   Test_Overload(d);  
}  
```  
  
 **출력**  
  
```Output  
overloaded +(String ^ a, String ^ b)   
  
overloaded +(String ^ a, Object ^ b)   
  
overloaded +(Object ^ a, String ^ b)   
  
String ^ a  
  
const char * a  
```  
  
 **예제**  
  
 다음 예제에서는 컴파일러가 네이티브 문자열 구분을 보여 줍니다. 및 <xref:System.String> 문자열입니다.  
  
```cpp  
// string_operators_3.cpp  
// compile with: /clr  
using namespace System;  
int func() {  
   throw "simple string";   // const char *  
};  
  
int func2() {  
   throw "string" + "string";   // returns System::String  
};  
  
template<typename T>  
void func3(T t) {  
   Console::WriteLine(T::typeid);  
}  
  
int main() {  
   try {  
      func();  
   }  
   catch(char * e) {  
      Console::WriteLine("char *");  
   }  
  
   try {  
      func2();  
   }  
   catch(String^ str) {  
      Console::WriteLine("String^ str");  
   }  
  
   func3("string");   // const char *  
   func3("string" + "string");   // returns System::String  
}  
```  
  
 **출력**  
  
```Output  
char *  
  
String^ str  
  
System.SByte*  
  
System.String  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼의 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)   
 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)