---
title: dllexport, dllimport | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- dllimport_cpp
- dllexport_cpp
dev_langs:
- C++
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f21256ca78a4bf5f268c4fa3d03c86bc52c91670
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461678"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport
**Microsoft 전용**  
  
 합니다 **dllexport** 하 고 **dllimport** 저장소 클래스 특성은 C 및 c + + 언어에 대 한 Microsoft 전용 확장 합니다. 이러한 특성을 사용하여 함수, 데이터 및 개체를 DLL에 내보내거나 DLL에서 가져올 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
   __declspec( dllimport ) declarator  
   __declspec( dllexport ) declarator  
```  
  
## <a name="remarks"></a>설명  
 이러한 특성은 실행 파일이나 다른 DLL일 수 있는 클라이언트에 대한 DLL 인터페이스를 명시적으로 정의합니다. 함수 선언 **dllexport** 내보낸 함수의 사양 기준 이상 모듈 정의 (.def) 파일의 경우 필요 하지 않습니다. 합니다 **dllexport** 대체 특성을 **__export** 키워드입니다.  
  
 클래스가 declspec(dllexport)로 표시된 경우 클래스 계층 구조에 있는 클래스 템플릿의 특수화는 암시적으로 declspec(dllexport)로 표시됩니다. 이는 클래스 템플릿이 명시적으로 인스턴스화되었으며 클래스의 멤버가 정의되어야 함을 의미합니다.  
  
 **dllexport** 함수의 해당 트 데코 레이 된 이름의 함수를 노출 합니다. C++ 함수의 경우 여기에 이름 변환이 포함됩니다. C 함수 또는 `extern "C"`로 선언된 함수의 경우 여기에 호출 규칙을 기반으로 하는 플랫폼별 데코레이션이 포함됩니다. C/c + + 코드의 이름 데코레이션에 대 한 자세한 내용은 [데코 레이트 된 이름](../build/reference/decorated-names.md)합니다. `__cdecl` 호출 규칙을 사용하여 내보낸 C 함수 또는 C++ `extern "C"` 함수에는 이름 데코레이션이 적용되지 않습니다.  
  
 데코레이트되지 않은 이름을 내보내려면 EXPORTS 섹션에서 데코레이트되지 않은 이름을 정의하는 모듈 정의(.def) 파일을 사용하여 연결할 수 있습니다. 자세한 내용은 [내보내기를](../build/reference/exports.md)합니다. 데코레이팅되지 않은 이름을 내보내는 또 다른 방법은 사용 하는 것을 `#pragma comment(linker, "/export:alias=decorated_name")` 소스 코드에 지시문입니다.  
  
 선언 하는 경우 **dllexport** 또는 **dllimport**를 사용 해야 [확장 된 특성 구문은](../cpp/declspec.md) 하며 **__declspec** 키워드.  
  
## <a name="example"></a>예  
  
```cpp  
// Example of the dllimport and dllexport class attributes  
__declspec( dllimport ) int i;  
__declspec( dllexport ) void func();  
```  
  
 또는 매크로 정의를 사용하여 코드를 보다 읽기 쉽게 만들 수 있습니다.  
  
```cpp  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllImport int j;  
DllExport int n;  
```  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [정의 및 선언](../cpp/definitions-and-declarations-cpp.md)  
  
-   [dllexport 및 dllimport로 인라인 C++ 함수 정의](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
-   [일반 규칙 및 제한 사항](../cpp/general-rules-and-limitations.md)  
  
-   [C++ 클래스에서 dllimport 및 dllexport 사용](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [__declspec](../cpp/declspec.md)   
 [키워드](../cpp/keywords-cpp.md)