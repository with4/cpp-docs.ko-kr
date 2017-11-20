---
title: "변환: 진단 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb7f826be88ebec640a6f3b40b38478eea91ed36
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="translation-diagnostics"></a>변환: 진단
**ANSI 2.1.1.3** 진단 식별 방법  
  
 Microsoft C는 다음의 경우에 형식에서 오류 메시지를 생성합니다.  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 *파일 이름*이 오류가 발견된 소스 파일의 이름일 경우, *줄 번호*가 컴파일러 오류가 발견된 줄 번호일 경우, `diagnostic`이 "오류" 또는 "경고"일 경우, `number`가 오류 또는 경고를 식별하는 고유한 네 자리 디지털 숫자(**C** 뒤에 위치, 구문 설명 참조)일 경우, `message`가 설명 메시지일 경우입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Implementation-Defined Behavior](../c-language/implementation-defined-behavior.md)