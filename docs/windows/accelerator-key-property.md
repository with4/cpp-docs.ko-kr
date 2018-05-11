---
title: 액셀러레이터 키 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4fc56384d666026f4cc7e21f9d8af9347046fd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="accelerator-key-property"></a>액셀러레이터 키 속성
다음은 액셀러레이터 키 테이블의 키 속성에 대해 사용할 수 있는 항목입니다.  
  
-   0에서 10 진수 형식에서 255 사이의 정수입니다. 값 값 ASCII 또는 ANSI로 다음과 같이 처리 됩니다 있는지 여부를 결정 합니다.  
  
    -   한 자리 숫자는 항상 해당 키가 아닌 ASCII 또는 ANSI 값으로 해석 됩니다.  
  
    -   부터 26 앞에 0, 1에서 값으로 해석 됩니다 ^ A-^ Z 영문자를 누르고 CTRL 키와 함께 누른 경우 문자의 ASCII 값을 나타냅니다.  
  
    -   27 32 까지의 값은 항상 027 032부터 3 자리 10 진수 값으로 해석 됩니다.  
  
    -   부터 255 033에서 값 앞에 0의 있든지 하지 ANSI 값으로 해석 됩니다.  
  
-   단일 키보드 문자입니다. 대문자 A-Z 또는 ASCII 또는 가상 키 값이 있습니다; 숫자는 0-9 가능 다른 모든 문자는 ASCII만 있습니다.  
  
-   단일 키보드 문자 A-Z 범위의 (대문자), 캐럿 (^) 뒤에 옵니다 (예를 들어 ^ C). 이 CTRL 키를 누르면 키의 ASCII 값을 입력 합니다.  
  
    > [!NOTE]
    >  ASCII 값을 입력할 때는 한정자 속성 옵션이 제한 됩니다. 사용 하기 위해 사용할 수 있는 유일한 제어 키는 ALT 키가입니다.  
  
-   유효한 가상 키 식별자입니다. 액셀러레이터 키 테이블의 드롭 다운 키 상자에는 표준 가상 키 식별자의 목록을 포함합니다.  
  
    > [!TIP]
    >  하나 또는 액셀러레이터 키 테이블의 여러 항목을 마우스 오른쪽 단추로 클릭 한 다음 선택 합니다는 액셀러레이터 키를 정의 하는 또 다른 방법은 **다음 입력 된 키** 바로 가기 메뉴에서 한 다음 키 또는 키 조합을 바로 가기 키를 누릅니다. **다음 입력 된 키** 명령에서 제공 됩니다.는 **편집** 메뉴.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 속성 설정](../windows/setting-accelerator-properties.md)   
 [액셀러레이터 키 테이블에서 편집](../windows/editing-in-an-accelerator-table.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)