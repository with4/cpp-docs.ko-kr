---
title: 액셀러레이터 키 형식 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb1ba8f117fadab7cccb835ba8889d57bcc9f184
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856503"
---
# <a name="accelerator-type-property"></a>액셀러레이터 키 형식 속성
액셀러레이터 키 **형식** 속성은 액셀러레이터 키 ID와 연결 된 바로 가기 키 조합을 가상 키 조합 또는 ASCII/ANSI 키 값을 확인 합니다.  
  
-   경우는 **형식** 속성은 **ASCII**, [한정자](../windows/accelerator-modifier-property.md) 만 될 또는 Alt 또는 CTRL 키를 사용 하는 액셀러레이터 키를 가질 수 있습니다 (키 앞에 의해 지정 된는 ^).  
  
-   경우는 **형식** 속성은 **VIRTKEY**, 한정자 및 키 값의 조합이 유효 합니다.  
  
    > [!NOTE]
    >  액셀러레이터 키 테이블에 값을 입력 한 값이 ASCII/ANSI로 처리 하려는 경우에 테이블의 항목에 대 한 유형 및 드롭다운 목록에서에서 선택 ASCII 클릭 하면 됩니다. 그러나 사용 하는 경우는 **다음 입력 된 키** 명령 (**편집** 메뉴) 키를 지정 하려면 리소스는 **형식** 속성 VIRTKEY에서 ASCII *하기전에* 키 코드를 입력 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 속성 설정](../windows/setting-accelerator-properties.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)