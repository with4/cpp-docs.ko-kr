---
title: HTTP 기초 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a2692edd9d41f80023e44f4ca8172cba8f9d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="http-basics"></a>HTTP 기초
인터넷 응용 프로그램을 작성할 때 자주 검토 하 고 있습니다 HTTP 헤더의 정보를 추가 합니다. 반환 코드는 요청 된 이벤트의 성공 여부를 나타냅니다. 몇 가지 일반적인 반환 코드는 다음 표에 나열 됩니다.  
  
|반환 코드|의미|  
|-----------------|-------------|  
|200|URL을 찾음, 전송 수행|  
|400|인식할 수 없는 요청|  
|404|요청 URL을 찾을 수 없습니다.|  
|405|서버가 요청 된 메서드를 지원 하지 않습니다.|  
|500|알 수 없는 서버 오류|  
|503|서비스를 사용할 수 없음|  
  
 HTTP 응답에는 다음 표에 나와 있는 것 처럼 그룹화 됩니다.  
  
|그룹화|의미|  
|-----------|-------------|  
|200-299|성공|  
|300-399|정보|  
|400-499|요청 오류|  
|500-599|서버 오류|  
  
 하이퍼텍스트 전송 프로토콜 (HTTP)는 하이퍼미디어 정보 시스템에 대 한 응용 프로그램 수준 프로토콜. HTTP 및 웹 브라우저와 서버가 통신 하는 방법에 대 한 자세한 내용은 하이퍼텍스트 전송 프로토콜 (HTTP) 사양을 참조:  
  
 [http://www.w3.org/pub/WWW/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

