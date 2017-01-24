---
title: "String  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string support with /clr"
  - "/clr compiler option [C++], string support"
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 컴파일러는 일련의 문자 시퀀스로 표현되는 개체인 *문자열*을 지원합니다.  Visual C\+\+는 문자열 값이 명시적으로 인용된 스트링 값을 갖는 리터럴과 암시적인 값을 갖는 스트링 변수를 지원합니다.  
  
## 모든 런타임  
 할당된 메모리를 갖는 개체로 스트링을 표현하는 Windows 런타임 및 공용 언어 런타임은 자동적으로 관리됩니다.  즉, 스트링 변수가 범위를 벗어나거나 응용 프로그램이 종료될 때 스트링의 메모리를 명시적으로 버리는 것을 요구하지 않습니다.  문자열 개체의 수명을 자동적으로 관리되는 것을 나타내려면, [핸들 개체 \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) 한정자로 스트링 형식을 선언합니다.  
  
## Windows 런타임\(Windows Runtime\)  
 Windows 런타임 아키텍처는 `Platform` 네임 스페이스에서 `String` 데이터 형식을 구현하기 위해 Visual C\+\+가 필요합니다.  편의를 위해, Visual C\+\+는 또한 `string` 데이터 형식을 제공하는데, 이 형식은  `Platform::String`가 `default` 네임 스페이스에서 쓰이는 것과 동의어입니다.  
  
### 구문  
  
```cpp  
  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### 설명  
 스트링에 대한 자세한 내용과 예제를 보려면 [Platform::String, std::wstring, and Literals \(Platform\)](http://msdn.microsoft.com/ko-kr/ec92fbc6-edf3-4137-a85e-8e29bdb857a8)을 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 이 항목은 **\/clr** 컴파일러 옵션을 사용하여 Visual C\+\+ 컴파일러가 스트링 리터럴을 처리하는 방법을 보여줍니다.  **\/clr**를 사용하려면, 공용 언어 런타임 \(CLR\), C\+\+\/CLI 구문과 관리된 개체를 사용해야 합니다.  **\/clr**에 대한 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
 **\/clr**로 컴파일 하는 경우, 컴파일러는 문자열 리터럴 형식의 문자열을 <xref:System.String>의 형식으로 변환합니다.  기존 코드와의 호환성 유지를 하기 위한 이 두 가지 예외가 다음과 같습니다.  
  
-   예외 처리.  문자열 리터럴이 발생 하면, 컴파일러는 문자열 리터럴로 캐치합니다.  
  
-   템플릿 추론.  문자열 리터럴이 템플릿 인수로 전달된 경우, 컴파일러는 <xref:System.String>로 변환하지 않습니다.  제네릭 인수로 전달된 문자열 리터럴은 <xref:System.String>로 승격되는 것을 참조하세요.  
  
 컴파일러는 동작을 사용자 지정 하기 위해 재정의할 수 있는 기본적인 세 가지 연산자가 있습니다.  
  
-   System::String ^ 연산자 \+ \( System::String, System::String\).  
  
-   System::String ^ 연산자 \+ \( System::Object, System::String\).  
  
-   System::String ^ 연산자 \+ \( System::String, System::Object\).  
  
 <xref:System.String>를 전달할 때, 컴파일러는 필요에 따라 입력한 다음 문자열을 사용하여 \(ToString을 사용하여\) 개체를 연결할 합니다.  
  
 **\/clr:oldSyntax**로 컴파일 할 경우, 문자열 리터럴은 <xref:System.String>로 변환되지 않을 것입니다.  
  
> [!NOTE]
>  캐럿 \("^"\)은 선언된 변수가 C\+\+\/CLI 관리 개체를 위한 핸들인 것을 나타냅니다.  
  
 자세한 내용은 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)를 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 코드 예제에서는 문자열을 결합하고 비교하는 방법을 보여 줍니다.  
  
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
  
 **Output**  
  
  **abcdef**  
 **abcghi**  
 **ghiabc**  
 **c**  
 **abcdefghi**  
 **abczzz**  
 **abc1**  
 **abc97**  
 **abc3.1**  
 **abcdef**  
 **a 와 b는 같습니다**  
 **a와 b는 같지 않습니다.**  
 **abc**  
 **n은 비어 있습니다.** **예제**  
  
 다음 예제는 컴파일러에서 제공한 연산자를 오버 로드할 수 있고 <xref:System.String> 형식에 따라 함수 오버 로드를 찾을 수 있는 컴파일러를 보여줍니다.  
  
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
  
 **Output**  
  
  **오버로드된 \+\(문자열 ^ a, 문자열 ^ b\)**   
 **오버로드된 \+ \(문자열 ^ a, 개체 ^ b\).**   
 **오버로드된 \+ \(개체 ^ a, 문자열 ^ b\).**   
 **문자열 ^ a**  
 **const char \* a** **예제**  
  
 다음 샘플은 컴파일러가 네이티브 문자열과 <xref:System.String> 문자열을 구분하는 것을 보여줍니다.  
  
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
  
 **Output**  
  
  **char\***  
 **String ^ str**  
 **System.SByte\***  
 **System.String**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)   
 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)