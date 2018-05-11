---
title: 액셀러레이터 키 한정자 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d99d4656f2835f9adb60f310e429c4ccb97ac7b6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
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