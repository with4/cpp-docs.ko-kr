---
title: "액셀러레이터 키 속성 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83eea84c89a9f9873b687333b7454d9f3c9c41b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-accelerator-properties"></a>액셀러레이터 키 속성 설정
액셀러레이터 키 속성을 설정할 수는 [속성 창](/visualstudio/ide/reference/properties-window) 언제 든 지 합니다. 또한 액셀러레이터 키 편집기를 사용하여 액셀러레이터 키 테이블에서 액셀러레이터 키 속성을 수정할 수 있습니다. 속성 창 또는 액셀러레이터 키 편집기를 사용하여 변경한 내용은 결과가 동일합니다. 편집 내용은 액셀러레이터 키 테이블에 바로 반영됩니다.  
  
 세 가지 속성에 대 한 각 가속기 [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   [한정자 속성](../windows/accelerator-modifier-property.md) 컨트롤 액셀러레이터 키에 대 한 키 조합을 설정 합니다.  
  
    > [!NOTE]
    >  속성 창에서 이 속성은 세 가지 별도의 부울 속성으로 나타나며, Alt, Ctrl 및 Shift 모두 독립적으로 제어할 수 있습니다.  
  
-   [키 속성](../windows/accelerator-key-property.md) 액셀러레이터로 사용할 실제 키를 설정 합니다.  
  
-   [Type 속성](../windows/accelerator-type-property.md) 키 가상 (VIRTKEY) 또는 ASCII/ANSI로 해석 되는지 여부를 결정 합니다.  
  

  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [미리 정의 된 액셀러레이터 키](../windows/predefined-accelerator-keys.md)   
 [리소스 편집기](../windows/resource-editors.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)