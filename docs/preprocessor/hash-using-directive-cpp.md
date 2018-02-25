---
title: "#using 지시문 (C + + /cli CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs:
- C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1c43acde6e4f755c6757fc933c80091ba05927c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="using-directive-cclr"></a>#using 지시문 (C + + /cli CLR)
메타 데이터를 사용 하 여 컴파일된 프로그램으로 가져오는 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `file`  
 MSIL .dll, .exe, .netmodule 또는. obj 예를 들어 개체에 적용된  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 `file`의 모든 형식을 액세스할 수 있도록 지정합니다.  자세한 내용은 참조 [Friend 어셈블리 (c + +)](../dotnet/friend-assemblies-cpp.md)합니다.  
  
## <a name="remarks"></a>설명  
 `file`은 관리되는 데이터와 관리되는 구문에 대해 가져오는 MSIL(Microsoft 중간 언어) 파일이 될 수 있습니다. 경우.dll 파일에는 어셈블리 매니페스트가 가져온 매니페스트에서 참조 하는 모든.dll 및 작성 하는 어셈블리는 나열 *파일* 어셈블리 참조로 메타 데이터에 있습니다.  
  
 경우 `file` 어셈블리를 포함 하지 않습니다 (경우 `file` 는 모듈) 방금 모듈에 일부 인지를 나타내는 옵션이 현재 (어셈블리) 응용 프로그램의 모듈에서 형식 정보를 사용 하지 않을 경우와 어셈블리는 사용.[/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)합니다. 그러면 어셈블리를 참조하는 모든 응용 프로그램에서 모듈의 형식을 사용할 수 있습니다.  
  
 사용 하는 대신 `#using` 는 [/FU](../build/reference/fu-name-forced-hash-using-file.md) 컴파일러 옵션입니다.  
  
 에 전달 된.exe 어셈블리 `#using` 컴파일해야 할지.NET Visual Studio 컴파일러 (Visual Basic 또는 Visual C#, 예를 들어) 중 하나를 사용 하 여 합니다.  사용 하 여 컴파일된.exe 어셈블리에서 메타 데이터를 가져오는 **/clr** 파일 로드 예외가 발생 합니다.  
  
> [!NOTE]
>  `#using`으로 참조된 구성 요소는 컴파일 시 가져온 다른 버전의 파일과 실행 가능하므로 클라이언트 응용 프로그램에서 예기치 않은 결과가 발생할 수 있습니다.  
  
 컴파일러가 어셈블리 (모듈 아님)의 형식을 인식할 수 순서로 할 수 있는, 예를 들어 형식의 인스턴스를 정의 하 여 해당 형식을 확인할 되도록 강제 해야 합니다. 다른 여러 가지 예를 들어 컴파일러에 대 한 어셈블리의 형식 이름을 확인 하는 어셈블리의 형식에서 상속 하는 경우, 형식 이름은 다음 장치는 알려진 컴파일러에 있습니다.  
  
 사용 된 소스 코드에서 작성 된 메타 데이터를 가져올 때 [__declspec (thread)](../cpp/thread.md), 메타 데이터에서 스레드 의미 체계가 유지 되지 않습니다. 선언 된 변수는 예를 들어 **__declspec (thread)**,.NET Framework 공용 언어 런타임에 대 한 빌드를 통해 가져온 프로그램에서 컴파일된 `#using`, 더 이상 **__declspec ( 스레드)** 변수에 의미 합니다.  
  
 `#using`에 의해 참조되는 파일에서 가져온 모든 형식(관리 및 네이티브)을 사용할 수 있지만 네이티브 형식은 컴파일러에서 정의가 아닌 선언으로 처리됩니다.  
  
 로 컴파일하는 경우 mscorlib.dll은 자동으로 참조 됩니다 **/clr**합니다.  
  
 LIBPATH 환경 변수는 컴파일러가 `#using`으로 전달된 파일 이름을 확인할 때 검색할 디렉터리를 지정합니다.  
  
 컴파일러는 다음과 같은 경로에 따라 참조를 검색합니다.  
  
-   `#using` 문에서 지정된 경로  
  
-   현재 디렉터리입니다.  
  
-   .NET Framework 시스템 디렉터리  
  
-   으로 추가 된 디렉터리는 [/AI](../build/reference/ai-specify-metadata-directories.md) 컴파일러 옵션입니다.  
  
-   LIBPATH 환경 변수의 디렉터리  
  
## <a name="example"></a>예  
 어셈블리(C)를 빌드하고 다른 어셈블리(A)를 참조하는 어셈블리(B)를 참조하는 경우 C에서 A 형식 중 하나를 명시적으로 사용하지 않는 한 어셈블리 A를 명시적으로 참조할 필요가 없습니다.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>예  
  
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
  
## <a name="example"></a>예  
 다음 샘플에서는 프로그램이 using_assembly_A.cpp에 정의된 형식 중 하나를 사용하지 않으므로 using_assembly_A.dll을 사용하여 참조하지 않는 컴파일러 오류가 발생하지 않습니다.  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)