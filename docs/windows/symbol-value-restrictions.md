---
title: 기호 값 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.value
dev_langs:
- C++
helpviewer_keywords:
- symbols, value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3432ca82d9557fbcb47da65be148bedb0f47f8b8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889556"
---
# <a name="symbol-value-restrictions"></a>기호 값 제한
기호 값은 #define 전처리기 지시문에 대해 일반적인 방식으로 표현된 정수일 수 있습니다. 다음은 기호 값의 몇 가지 예입니다.  
  
```  
18  
4001  
0x0012  
-3456  
```  
  
 리소스(액셀러레이터 키, 비트맵, 커서, 대화 상자, 아이콘, 메뉴, 문자열 테이블 및 버전 정보)에 대한 기호 값은 0에서 32,767 사이의 10진수여야 하며 16진수일 수 없습니다. 대화 상자 컨트롤이나 문자열 테이블의 개별 문자열 같이 리소스 일부에 대한 기호 값은 0에서 65,534 사이이거나 -32,768에서 32,767 사이일 수 있습니다.  
  
 리소스 기호는 16비트 숫자입니다. 이 기호는 부호 있는 숫자나 부호 없는 숫자로 입력할 수 있지만 내부적으로는 부호 없는 정수로 사용됩니다. 따라서 음수는 해당 양수 값으로 캐스팅됩니다.  
  
 다음은 기호 값에 대한 몇 가지 제한 사항입니다.  
  
-   Visual Studio 개발 환경 및 MFC에서는 일부 숫자 범위를 특별한 용도로 사용합니다. 가장 중요한 비트 세트를 사용하는 모든 숫자(부호에 따라 -32,768 ~ -1 또는 32,768 ~ 65,534)는 MFC에 의해 예약되었습니다.  
  
-   기호 값은 다른 기호 문자열을 사용하여 정의할 수 없습니다. 예를 들어 다음과 같은 기호 정의는 지원되지 않습니다.  
  
    ```  
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported  
    ```  
  
-   인수가 있는 전처리기 매크로는 값 정의로 사용할 수 없습니다. 예를 들어:  
  
    ```  
    #define   IDD_ABOUT  ID(7) //not supported  
    ```  
  
     컴파일 시간에 `ID`가 계산되는 결과에 관계없이 유효한 식이 아닙니다.  
  
-   응용 프로그램에 식으로 정의된 기호를 포함하는 기존 파일이 있을 수 있습니다. 읽기 전용 기호로 포함 하는 방법에 대 한 자세한 내용은 참조 하십시오. [공유 (읽기 전용) 또는 계산 된 기호](../windows/including-shared-read-only-or-calculated-symbols.md)합니다.  
  
 숫자 범위에 대 한 자세한 내용은 참조 하십시오. [TN023: 표준 MFC 리소스](../mfc/tn023-standard-mfc-resources.md)합니다.  
  

  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [기호 숫자 값 변경](../windows/changing-a-symbol-s-numeric-value.md)   
 [기호 이름 제한](../windows/symbol-name-restrictions.md)   
 [미리 정의된 기호 ID](../windows/predefined-symbol-ids.md)