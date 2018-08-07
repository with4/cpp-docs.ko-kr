---
title: partial (c + + 구성 요소 확장명) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- partial_CPP
dev_langs:
- C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71c0fc9739e7ef8e1e68c5678ce56fcec4a250c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880181"
---
# <a name="partial--c-component-extensions"></a>partial(C++ 구성 요소 확장)
`partial` 키워드를 사용 하면 서로 다른 동일한 ref 클래스를 독립적으로 및 서로 다른 파일에서 작성할 수 있습니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능은 Windows Runtime에만 적용 됨)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 Ref 클래스에 두 개의 부분 정의 대해서는 `partial` 키워드는 맨 처음 발견 되는 정의에 적용 되며이 휴먼 코더 키워드를 매우 자주 사용 하지 않는 있도록 일반적으로 자동 생성 된 코드에 의해 수행 됩니다. 클래스의 모든 후속 부분 정의 생략는 `partial` 한정자는 *클래스 키* 키워드 및 클래스 식별자입니다. 이전에 정의한 ref 클래스 및 클래스 식별자 있지만 컴파일러의 발생 했을 때 `partial` 키워드를 내부적으로 결합 하 여 모든 한 정의에 ref 클래스 정의의 부분입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
partial class-key identifier {  
   /* The first part of the partial class definition. 
      This is typically auto-generated */  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same 
      identifier is specified, but the "partial" keyword is omitted. */  
}  
```  
  
### <a name="parameters"></a>매개 변수  
 *클래스 키*  
 클래스 또는 구조체는 Windows 런타임에서 지원 되는 선언 하는 키워드입니다. 어느 `ref class`, `value class`, `ref struct`, 또는 `value struct`합니다.  
  
 *identifier*  
 형식 정의의 이름입니다.  
  
### <a name="remarks"></a>설명  
 Partial 클래스에서는 한 개의 파일과 자동 코드 생성 소프트웨어의 클래스 정의의 한 부분을 수정 하는 시나리오를 지원-예를 들어 XAML 디자이너-다른 파일에는 같은 클래스에 코드를 수정 합니다. Partial 클래스를 사용 하 여 코드를 덮어쓰지 자동 코드 생성기를 방지할 수 있습니다. Visual Studio 프로젝트에서는 생성된 파일에 `partial` 한정자가 자동으로 적용됩니다.  
  
 내용: 두 가지 예외가 partial 클래스 정의 수 있는 모든 포함 될 경우 전체 클래스 정의 포함 될 수는 `partial` 키워드를 생략 했습니다. 그러나 클래스 액세스 가능성(예: `public partial class X { ... };`) 또는 `declspec`을 지정할 수 없습니다.  
  
 액세스 지정자에 대 한 partial 클래스 정의에 사용 된 *식별자* 기본 액세스 가능성에 대 한 후속 부분 또는 전체 클래스 정의에 영향을 주지 않으므로 *식별자*합니다. 정적 데이터 멤버의 인라인 정의가 허용 됩니다.  
  
 선언은 클래스의 부분 정의 *식별자* 만 생성 이름을 *식별자*, 하지만 *식별자* 클래스를 필요로 하는 방법에 사용할 수 없습니다 정의 합니다. 이름 *식별자* 의 크기를 알아야 하는 데 사용할 수 없습니다 *식별자*, 기본 또는의 멤버를 사용 하도록 또는 *식별자* 될 때까지 컴파일러가의 전체 정의 발견 한 후 *식별자*합니다.  
  
 번호 및 순서 지정:에 0 개 이상의 부분 클래스 정의가 있을 수 있습니다 *식별자*합니다. 모든 부분 클래스 정의 *식별자* 어휘 적으로의 전체 정의 앞에 야 *식별자* (전체 정의가; 없는 경우 이렇게 하지 않으면 클래스 사용할 수 처럼 정방향 선언)의 정방향 선언 앞에 오지 필요 하지만 *식별자*합니다. 모든 클래스 키가 일치 해야 합니다.  
  
 전체 정의: 클래스의 전체 정의 지점 *식별자*, 동작은 동일 처럼의 정의 *식별자* 가 모든 기본 클래스, 멤버 등를 순서 대로 선언한 것 발생 했으며 partial 클래스에 정의 되어 있습니다.  
  
 템플릿: partial 클래스는 템플릿일 수 없습니다.  
  
 제네릭: partial 클래스 될 수 있습니다는 일반 전체 정의 제네릭 수 있습니다. 하지만 모든 일부 또는 전체 클래스에는 정확히 동일한 제네릭 매개 변수, 형식 매개 변수 이름을 포함 하 여가 있어야 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `partial` 키워드를 참조 [Partial 클래스 (C + + /cli CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 (이 언어 기능은 공용 언어 런타임에는 적용 되지 않습니다.)  
  
## <a name="see-also"></a>참고 항목  
 [Partial 클래스 (C + + /cli CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)