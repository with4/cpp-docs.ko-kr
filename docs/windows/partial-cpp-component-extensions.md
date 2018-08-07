---
title: partial (c + + 구성 요소 확장) | Microsoft Docs
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
ms.openlocfilehash: 82bd3baab698e013b3bfe506877bbdbf0021794b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605934"
---
# <a name="partial--c-component-extensions"></a>partial(C++ 구성 요소 확장)
합니다 **부분** 키워드 독립적이 고 다른 파일에 작성 동일한 ref 클래스의 다른 부분을 사용 하도록 설정 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 (이 언어 기능 Windows 런타임에만 적용 됩니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
 두 개의 partial 정의 된 ref 클래스는 **부분** 키워드 맨 처음 발견 되는 정의에 적용 되 고 일반적으로 이렇게 자동으로 생성 된 코드에 의해 휴먼 코더 키워드를 자주 사용 하지 않도록 합니다. 클래스의 모든 후속 부분 정의 생략 합니다 **부분** 한정자를 *클래스 키* 키워드 및 클래스 식별자입니다. 발견할 경우에 컴파일러는 이전에 정의한 ref 클래스 및 클래스 식별자 이지만 **부분** 키워드를 내부적으로 결합 하 여 모든 한 정의를 ref 클래스 정의의 부분입니다.  
  
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
 키워드는 클래스 또는 구조체는 Windows 런타임에서 지원 되는 선언입니다. 어느 **ref 클래스**를 **값 클래스**를 **ref 구조체**, 또는 **값 구조체**합니다.  
  
 *identifier*  
 정의 된 형식의 이름입니다.  
  
### <a name="remarks"></a>설명  
 Partial 클래스는 하나의 파일에 자동 코드 생성 소프트웨어 클래스 정의의 한 부분을 수정할 수 있는 시나리오를 지원-예를 들어, XAML 디자이너-다른 파일에서 동일한 클래스의 코드를 수정 합니다. Partial 클래스를 사용 하 여 코드를 덮어쓰지 자동 코드 생성기를 방지할 수 있습니다. Visual Studio 프로젝트에는 **부분** 한정자는 생성된 된 파일에 자동으로 적용 됩니다.  
  
 콘텐츠: 두 가지 예외를 사용 하 여 partial 클래스 정의 무엇이 든 포함할 수는 경우 전체 클래스 정의 포함할 수 있는 합니다 **부분** 키워드 생략 되었습니다. 그러나 클래스 액세스 가능성 지정할 수 없습니다 (예를 들어 `public partial class X { ... };`), 또는 **declspec**합니다.  
  
 액세스에 대 한 partial 클래스 정의에 사용 되는 지정자 *식별자* 기본 액세스 가능성에 대 한 후속 부분 또는 전체 클래스 정의에 영향을 주지 않습니다 *식별자*합니다. 정적 데이터 멤버의 인라인 정의가 허용 됩니다.  
  
 선언: 클래스의 부분 정의 *식별자* 만 이름을 도입 되었습니다 *식별자*, 하지만 *식별자* 클래스를 필요로 하는 방식으로 사용할 수 없습니다 정의 합니다. 이름을 *식별자* 의 크기를 몰라도 사용할 수 없습니다 *식별자*, 기본 또는의 멤버를 사용 하 여 *식별자* 될 때까지 컴파일러의 전체 정의 발견 한 후 *식별자*합니다.  
  
 번호 및 순서 지정:에 대 한 0 개 이상의 partial 클래스 정의가 있을 수 있습니다 *식별자*합니다. 모든 부분 클래스 정의 *식별자* 어휘의 하나의 완전 한 정의 빨라야 *식별자* (전체 정의가 있으면이 고, 그렇지 클래스를 사용할 수 없습니다 제외한 처럼 정방향 선언)의 전방 선언 앞에 오지 필요 하지만 *식별자*합니다. 모든 클래스 키가 일치 해야 합니다.  
  
 전체 정의: 클래스의 전체 정의 지점 *식별자*, 동작은 동일 처럼 정의 *식별자* 모든 기본 클래스, 멤버 등 나타나는 순서 대로 선언한 발견 되었으며 partial 클래스에서 정의 합니다.  
  
 템플릿: partial 클래스는 템플릿일 수 없습니다.  
  
 제네릭: partial 클래스가 될 수 있습니다 제네릭 전체 정의 제네릭이 될 수 있습니다. 있지만 모든 부분 및 전체 클래스에는 정확히 동일한 제네릭 매개 변수, 형식 매개 변수 이름을 포함 하 여 있어야 합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 합니다 **부분** 키워드를 참조 하세요 [Partial 클래스 (C + + CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 (이 언어 기능을 공용 언어 런타임에서 적용 되지 않습니다.)  
  
## <a name="see-also"></a>참고 항목  
 [Partial 클래스 (C + + /cli CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)