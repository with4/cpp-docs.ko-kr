---
title: "#using 지시문 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "friend_as_cpp"
  - "#using"
  - "friend_as"
  - "#using_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#using 지시문"
  - "LIBPATH 환경 변수"
  - "전처리기, 지시문"
  - "using 지시문(#using)"
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #using 지시문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\/clr](../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일된 프로그램에 메타 데이터를 가져온다.  
  
## 구문  
  
```  
#using file [as_friend]  
```  
  
#### 매개 변수  
 `file`  
 MSIL.dll,.exe,.netmodule 또는. obj.  예를 들면 다음과 같습니다.  
  
 `#using <MyComponent.dll>`  
  
 as\_friend  
 `file` 의 모든 형식이 액세스할 수 있도록 지정합니다.  자세한 내용은 [Friend 어셈블리\(C\+\+\)](../dotnet/friend-assemblies-cpp.md)을 참조하십시오.  
  
## 설명  
 `file` 은 관리되는 데이터와 관리되는 구문에 대해 가져오는 Microsoft 중간 언어 \(MSIL\) 파일이 될 수 있습니다.  모든 .dll 파일이 어셈블리 매니페스트를 포함하면 매니페스트에서 참조하는 모든.dll은 불러와지게 되고 빌드하는 어셈블리는 어셈플리 참조로 메타 데이터에서 *파일* 을 나열합니다.  
  
 만약 `file` 이 \( `file` 이 모듈일 때\) 어셈블리가 포함 되어 있지 않고 현재 \(어셈블리\)응용 프로그램에서 모듈로 부터의 형식 정보를 사용하지 않으면,모듈은 어셈블리의 부분임을 나타내는 옵션을 갖게 됩니다.; [\/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)을 사용합니다.  모듈에서 형식은 어셈블리를 참조하는 모든 응용 프로그램에 사용할 수 있습니다.  
  
 `#using` 을 사용하기 위한 대안은 [\/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션입니다.  
  
 `#using` 에 전달된 .exe 어셈블리는 **\/clr:safe** 또는 **\/clr:pure**를 사용하거나 \(예를 들어, Visual Basic 또는 Visual C\#\) 다른 Visual Studio 컴파일러를 사용하여 컴파일되어야 합니다.  **\/clr** 를 사용하여 컴파일된 .exe 어셈블리에서 메타데이터를 가져오는 것은 파일 로드 예외가 발생합니다.  
  
> [!NOTE]
>  `#using` 을 참조하는 구성 요소는 클라이언트 응용 프로그램에서 예기치 않은 결과가 발생하는 컴파일 타임에서 가져올 파일의 다른 버전을 사용하여 실행될 수 있습니다.  
  
 컴파일러가 모듈이 아니라 어셈블리에서 특정 형식을 인식하려면 해당 형식을 확인할 수 있어야 합니다. 예를 들면, 해당 형식의 인스턴스를 정의하여 형식을 확인할 수 있습니다.  컴파일러는 다른 방법을 사용하여 어셈블리에서 형식 이름을 확인할 수 있습니다. 예를 들어, 어셈블리에서 특정 형식을 상속하면 해당 형식 이름이 컴파일러에 전달됩니다.  
  
 [\_\_declspec\(thread\)](../cpp/thread.md)에 사용되는 소스 코드에서 작성된 메타 데이터를 가져올 때, 스레드 의미는 메타 데이터에 유지되지 않습니다.  예를 들어, **\_\_declspec\(thread\)**를 사용하여 선언된 변수, NET Framework 공용 언어 런타임에 대해 빌드된 프로그램에서 컴파일된 변수, `#using` 을 통해 가져와진 변수는 더 이상 변수에서 **\_\_declspec \(thread\)** 의미 체계를 갖지 않습니다.  
  
 `#using`에 의해 참조되는 파일에서 가져온 모든 형식 \(관리 및 네이티브\)을 사용할 수 있지만, 컴파일러 네이티브 는 형식 선언을 정의 하지 않는 것을 취급합니다.  
  
 **\/clr**을 사용하여 컴파일하는 경우에 자동으로 mscorlib.dll는 참조됩니다.  
  
 LIBPATH 환경 변수는 컴파일러가 `#using` 로 전달된 파일 이름을 확인하려고 할 때 검색될 디렉터리를 지정합니다.  
  
 컴파일러는 다음과 같은 경로에 따라 참조에 대해 검색합니다:  
  
-   `#using` 문에서 지정된 경로입니다.  
  
-   현재 디렉터리  
  
-   .NET Framework 시스템 디렉터리입니다.  
  
-   디렉터리는 [\/AI](../build/reference/ai-specify-metadata-directories.md) 컴파일러 옵션을 사용하여 추가됩니다.  
  
-   LIBPATH 환경 변수에 대한 디렉터리입니다.  
  
## 예제  
 사용자가 어셈블리 \(C\)와 또다른 어셈블리 \(A\)를 참조하는 어셈블리 \(B\)를 빌드하면, C에서 A의 형식을 명시적으로 사용하지 않을 경우 명시적으로 어셈블리 A를 참조하지 않아야 합니다.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## 예제  
  
```  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};  
  
```  
  
## 예제  
 다음 샘플에서는, 프로그램이 \_assembly\_A.cpp에 정의된 형식 중 하나를 사용하지 않으므로 \_assembly\_A.dll을 사용하여 참조를 하지 않는 컴파일러 오류가 발생하지 않습니다.  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)