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
ms.openlocfilehash: da825a4f2052f05b24ff724d709c7c8a4b6a3db3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645687"
---
# <a name="accelerator-type-property"></a>액셀러레이터 키 형식 속성
액셀러레이터 **형식** 속성은 액셀러레이터 키 ID와 연결 된 바로 가기 키 조합이 가상 키 조합 또는 ASCII/ANSI 키 값을 인지를 확인 합니다.  
  
-   경우는 **형식** 속성이 ASCII를 [한정자](../windows/accelerator-modifier-property.md) 만 될 `None` 또는 `Alt`를 사용 하는 액셀러레이터 키를 가질 수 있는 **Ctrl** (지정 된 키 키 앞에 `^`).  
  
-   경우는 **형식** 속성은 VIRTKEY를 조합 `Modifier` 및 `Key` 값이 잘못 되었습니다.  
  
    > [!NOTE]
    >  액셀러레이터 키 테이블에 값을 입력 하 고 값이 ASCII/ANSI 간단히 클릭으로 처리 하려는 경우는 **형식** 드롭다운 목록에서에서 선택 ASCII 테이블의 항목에 대 한 합니다. 그러나 사용 하는 경우는 **다음 입력 된 키** 명령 (**편집** 메뉴) 지정 하는 `Key`를 변경 해야 합니다는 **형식** ascii VIRTKEY속성*하기 전에* 입력을 `Key` 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 속성 설정](../windows/setting-accelerator-properties.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)