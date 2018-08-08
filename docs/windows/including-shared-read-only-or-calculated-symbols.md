---
title: 포함 하 여 공유 (읽기 전용) 또는 계산 된 기호 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.shared.calculated
dev_langs:
- C++
helpviewer_keywords:
- symbols, read-only
- symbols, shared
- symbols, calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 436ceb757f9cce5e1436b13f2d32a331295f4bf6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608614"
---
# <a name="including-shared-read-only-or-calculated-symbols"></a>공유(읽기 전용) 또는 계산된 기호 포함
다른 응용 프로그램에서 만든 리소스 파일을 처음으로 개발 환경에서 읽는 경우 포함된 헤더 파일을 모두 읽기 전용으로 표시합니다. 그런 다음, 사용할 수 있습니다는 [리소스 내용 대화 상자](../windows/resource-includes-dialog-box.md) 추가 읽기 전용 기호 헤더 파일을 추가 합니다.  
  
 읽기 전용 기호 정의를 사용하려는 한 가지 이유는 여러 프로젝트에서 공유하려고 하는 기호 파일 때문입니다.  
  
 또한 단순 정수 대신 식을 사용하여 기호 값을 정의하는 기호 정의를 사용하는 기존 리소스가 있는 경우에 포함된 기호 파일을 사용할 수 있습니다. 예를 들어:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 다음과 같은 경우 환경에서 이러한 계산된 기호를 올바르게 해석합니다.  
  
-   계산된 기호가 읽기 전용 기호 파일에 배치됩니다.  
  
-   리소스 파일에 이러한 계산된 기호가 이미 할당된 리소스가 포함되어 있습니다.  
  
-   숫자 식이 필요합니다.  
  
> [!NOTE]
>  문자열이나 숫자 식이 필요한 경우에는 식이 계산되지 않습니다.  
  
### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>리소스 파일에 공유(읽기 전용) 기호를 포함하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md).rc 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 [리소스 내용](../windows/resource-includes-dialog-box.md) 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 **읽기 전용 기호 지시문** 상자를 사용 합니다 **#include** 컴파일러 지시문을 읽기 전용 기호를 저장할 파일을 지정 합니다.  
  
     Resource.h는 주 기호 헤더 파일에 일반적으로 사용되는 파일 이름이므로 이 파일은 호출하지 마세요.  
  
    > [!NOTE]
    >  **중요 한** 입력 한 대로 정확 하 게 리소스 파일에 포함 된 읽기 전용 기호 지시문 상자에 입력 합니다. 입력한 내용에 맞춤법이나 구문 오류가 없는지 확인하세요.  
  
     사용 된 **읽기 전용 기호 지시문** 상자 기호 정의가 있는 파일을 포함 합니다. 리소스 정의는 포함하지 마세요. 그렇지 않으면 파일을 저장할 때 중복된 리소스 정의가 생성됩니다.  
  
3.  지정한 파일에 기호를 배치합니다.  
  
     이런 식으로 포함된 파일의 기호는 리소스 파일을 열 때마다 계산되지만 파일을 저장할 때 디스크에서 교체되지는 않습니다.  
  
4.  **확인**을 클릭합니다.  
  
## <a name="requirements"></a>요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [기호 이름 제한](../windows/symbol-name-restrictions.md)   
 [기호 값 제한](../windows/symbol-value-restrictions.md)   
 [미리 정의 된 기호 Id](../windows/predefined-symbol-ids.md)   
 [기호: 리소스 식별자](../windows/symbols-resource-identifiers.md)