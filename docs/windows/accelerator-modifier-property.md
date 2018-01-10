---
title: "액셀러레이터 키 한정자 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63d6a4b526fc1f2aeb2a942e682a8c7cc6f9b58c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-modifier-property"></a>액셀러레이터 키 한정자 속성
액셀러레이터 키 테이블의 한정자 속성에 대해 사용할 수 있는 항목은 다음과 같습니다.  
  
|값|설명|  
|-----------|-----------------|  
|**없음**|사용자가 키 값만 누릅니다. 이것은 가장 효과적으로 값과 함께 사용할는 ASCII/ANSI 001 026 통해으로 해석 됩니다 ^ A-^ Z (CTRL-A-Z, CTRL-).|  
|**Alt**|키 값 전에 ALT 키를 눌러야 합니다.|  
|**Ctrl**|키 값 전에 CTRL 키를 눌러야 합니다. ASCII 형식으로 유효 하지 않습니다.|  
|**Shift 키**|키 값 전에 SHIFT 키를 눌러야 합니다.|  
|**Ctrl + Alt**|CTRL 키와 키 값 하기 전에 ALT 키를 눌러야 합니다. ASCII 형식으로 유효 하지 않습니다.|  
|**Ctrl + Shift**|CTRL 키와 키 값 전에 SHIFT 키를 눌러야 합니다. ASCII 형식으로 유효 하지 않습니다.|  
|**Alt + Shift**|ALT 키와 키 값 전에 SHIFT 키를 눌러야 합니다. ASCII 형식으로 유효 하지 않습니다.|  
|**Ctrl + Alt + Shift**|사용자가 키를 누르면 CTRL, ALT 및 SHIFT 키 값입니다. ASCII 형식으로 유효 하지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 속성 설정](../windows/setting-accelerator-properties.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)