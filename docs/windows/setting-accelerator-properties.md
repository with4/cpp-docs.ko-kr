---
title: 액셀러레이터 키 속성 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d329d902014b3dff6f66fd6e3f1877a3bc70822
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016259"
---
# <a name="setting-accelerator-properties"></a>액셀러레이터 키 속성 설정
액셀러레이터 키 속성을 설정할 수 있습니다 합니다 [속성 창](/visualstudio/ide/reference/properties-window) 언제 든 지 합니다. 사용할 수도 있습니다는 **가속기** 액셀러레이터 키 테이블에서 액셀러레이터 키 속성을 수정 하는 편집기입니다. 사용 하 여 변경 합니다 **속성** 창 또는 **가속기** 편집기는 동일한 결과 얻은: 편집 액셀러레이터 키 테이블에 바로 반영 됩니다.  
  
 속성은 세 가지 각 accelerator [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160):  
  
-   합니다 [Modifier 속성](../windows/accelerator-modifier-property.md) 액셀러레이터 키 조합을 제어를 설정 합니다.  
  
    > [!NOTE]
    >  에 **속성** 창에서이 속성으로 나타납니다 세 가지 별도 부울 속성을 모두 제어할 수 있습니다 독립적으로: **Alt**합니다 **Ctrl**, 및 **Shift**합니다.  
  
-   합니다 [키 속성](../windows/accelerator-key-property.md) 액셀러레이터로 사용할 실제 키를 설정 합니다.  
  
-   합니다 [유형 속성](../windows/accelerator-type-property.md) 키 가상 (VIRTKEY) 또는 ASCII/ANSI로 해석 됩니다 있는지 여부를 결정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [미리 정의 된 액셀러레이터 키](../windows/predefined-accelerator-keys.md)   
 [리소스 편집기](../windows/resource-editors.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)