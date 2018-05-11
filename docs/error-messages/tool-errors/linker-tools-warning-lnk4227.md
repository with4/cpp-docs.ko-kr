---
title: 링커 도구 경고 LNK4227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b56617ee355654dfbb198252ea37cdb344950cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4227"></a>링커 도구 경고 LNK4227  
  
> 메타 데이터 작업 경고 (*HRESULT*): *warning_message*  
  
링커 병합할 때 메타 데이터 차이 검색 합니다.  
  
-   현재 구축 중인 어셈블리와 하나 이상의 참조 된 어셈블리입니다.  
  
-   하나 이상의 소스 코드 파일 컴파일에서 합니다.  
  
예를 들어 LNK4227 원인은 두 전역 함수의 이름이 같고 다르게 선언 된 매개 변수 정보를 설정한 경우 (즉, 선언이 모든 컴파일 대상에 일치 하지 않습니다). /TEXT ildasm.exe를 사용 하 여 /METADATA *object_file* 형식이 어떻게 다른 지 확인 하려면 각.obj 파일에 있습니다.  
  
LNK4227 다른 도구에서 발생 하는 문제를 보고에도 사용 됩니다. 자세한 내용은 경고 메시지를 검색 합니다.  
  
경고를 해결 하려면 메타 데이터 문제를 수정 해야 합니다.  
  
## <a name="example"></a>예제  
  
참조 된 어셈블리가 참조 하는 어셈블리와 다르게 서명 LNK4227 생성 됩니다.  
  
다음 샘플에서는 LNK4227 오류가 생성 됩니다.  
  
```cpp  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 그런 다음  
  
```cpp  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
## <a name="example"></a>예제  
  
잘못 된 형식으로 버전 번호는 어셈블리 특성에 전달 될 때 LNK4227 생성할 수도 있습니다.  ' *' 표기법은 관련 된 `AssemblyVersionAttribute`합니다.  이 경고를 해결 하려면 사용 하 여만에 번호를 버전 특성 이외의 `AssemblyVersionAttribute`합니다.  
  
다음 샘플에서는 LNK4227 오류가 생성 됩니다.  
  
```cpp  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```