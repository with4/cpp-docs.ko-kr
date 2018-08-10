---
title: 형식 전달 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, Visual C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 627b0a881795a963e3739accc351ee684b7b8232
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644936"
---
# <a name="type-forwarding-ccli"></a>형식 전달(C++/CLI)
*형식 전달* A. 어셈블리를 사용 하는 클라이언트를 다시 컴파일할 필요는 없습니다 되도록 다른 어셈블리 (어셈블리 B)에 형식 어셈블리 (어셈블리 A) 간에 이동할 수 있습니다  
  
## <a name="all-platforms"></a>모든 플랫폼  
 이 기능은 모든 런타임에서 지원 되지 않습니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 이 기능은 Windows 런타임에서 지원 되지 않습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 다음 코드 예제에서는 형식 전달을 사용 하는 방법을 보여 줍니다.  
  
### <a name="syntax"></a>구문  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### <a name="parameters"></a>매개 변수  
 *new*  
 어셈블리를 이동 하는 형식 정의입니다.  
  
 *type*  
 해당 정의 다른 어셈블리로 이동 하는 형식입니다.  
  
### <a name="remarks"></a>설명  
 구성 요소 (어셈블리)를 함께 제공 되 고 클라이언트 응용 프로그램에서 사용 하 고, 사용할 수 있습니다 (어셈블리) 구성 요소에서 형식을 다른 어셈블리로 이동, 업데이트 된 구성 요소 (및 필요한 추가 어셈블리)를 출시에 전달 하는 형식 및 클라이언트 응용 프로그램 다시 컴파일하지 않고 계속 작동 합니다.  
  
 기존 응용 프로그램에서 참조 하는 구성 요소에 대 한 형식 전달 에서만 작동 합니다. 응용 프로그램을 빌드하면 응용 프로그램에서 사용 되는 모든 형식에 대 한 적절 한 어셈블리 참조 여야 합니다.  
  
 어셈블리에서 형식 (유형 A)를 전달 하는 경우 추가 해야 합니다 `TypeForwardedTo` 어셈블리 참조 뿐만 아니라 해당 형식에 대 한 특성입니다. 참조 된 어셈블리 중 하나를 포함 해야 합니다.  
  
-   1. 형식 정의  
  
-   `TypeForwardedTo` 어셈블리 참조 뿐만 아니라 형식에 대 한 특성입니다.  
  
 전달 될 수 있는 형식의 예입니다.  
  
-   ref 클래스  
  
-   값 클래스  
  
-   열거형  
  
-   인터페이스  
  
 다음 형식을 전달할 수 없습니다.  
  
-   제네릭 형식  
  
-   네이티브 형식  
  
-   중첩 형식 (중첩된 된 형식을 전달 하려는 경우 전달 해야 합니다는 바깥쪽 형식)  
  
 공용 언어 런타임을 대상으로 하는 모든 언어로 작성 된 어셈블리에 형식을 전달할 수 있습니다.  
  
 따라서 A.dll 어셈블리를 빌드하는 데는 소스 코드 파일 형식 정의 포함 하는 경우 (`ref class MyClass`), 해당 형식을 이동 하 고 싶은 경우 B.dll 어셈블리에 정의:  
  
1.  이동 된 `MyClass` 형식 B.dll을 빌드하는 데 사용 하는 소스 코드 파일을 정의 합니다.  
  
2.  B.dll 어셈블리 빌드  
  
3.  삭제는 `MyClass` A.dll, 빌드 및 다음으로 대체 하는 데 사용 되는 소스 코드에서 정의 입력 합니다.  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  A.dll 어셈블리를 빌드하십시오.  
  
5.  클라이언트 응용 프로그램을 다시 컴파일하지 않고도 A.dll을 사용 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`