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
ms.openlocfilehash: 36884376e5ff31754e4c53ef6602f6bfd129f4a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650445"
---
# <a name="accelerator-key-property"></a>액셀러레이터 키 속성
다음은 액셀러레이터 키 테이블의 키 속성에 대해 사용할 수 있는 항목입니다.  
  
-   0과 10 진수 형식에서 255 사이의 정수입니다. 값을 값 ASCII 또는 ANSI로 다음과 같이 처리 됩니다 있는지 여부를 결정 합니다.  
  
    -   한 자리 숫자는 항상 ASCII 또는 ANSI 값이 아닌 해당 키로 해석 됩니다.  
  
    -   1부터 26 앞에 0을 값으로 해석 됩니다 ^ A-^ 영문자와 함께 누른 경우 문자의 ASCII 값을 나타내는 Z를 **Ctrl** 키를 누른 상태.  
  
    -   27부터 32 까지의 값은 항상 027 032부터 세 자리 10 진수 값으로 해석 됩니다.  
  
    -   앞에 0 또는 ANSI 값으로는 해석 되지 않는에서 033에서 255 사이의 값입니다.  
  
-   단일 키보드 문자입니다. A-Z를 대문자 또는 숫자는 0-9 ASCII 또는 가상 키 값 수 만 다른 문자가 ASCII입니다.  
  
-   A-Z 범위의 단일 키보드 문자 (대문자)를 앞에 캐럿 (^) (예를 들어 ^ C). 가이 사용 하 여 누르면 키의 ASCII 값을 입력 합니다 **Ctrl** 키를 누르고 있습니다.  
  
    > [!NOTE]
    >  ASCII 값을 입력 하는 경우 한정자 속성 옵션이 제한 됩니다. 사용 하기 위해 사용할 수 있는 유일한 컨트롤 키가 합니다 **Alt** 키입니다.  
  
-   모든 유효한 가상 키 식별자입니다. 액셀러레이터 키 테이블의 드롭 다운 키 상자에는 표준 가상 키 식별자의 목록을 포함합니다.  
  
    > [!TIP]
    >  액셀러레이터 키를 정의 하는 또 다른 방법은 또는 액셀러레이터 키 테이블에서 여러 항목을 마우스 오른쪽 단추로 클릭을 선택 하는 것 **다음 입력 된 키** 바로 가기 메뉴에서 한 다음 키보드의 키 또는 키 조합 중 하나를 누릅니다. 합니다 **다음 키 입력** 명령에서 제공 됩니다. 합니다 **편집** 메뉴.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 속성 설정](../windows/setting-accelerator-properties.md)   
 [액셀러레이터 키 테이블에서 편집](../windows/editing-in-an-accelerator-table.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)