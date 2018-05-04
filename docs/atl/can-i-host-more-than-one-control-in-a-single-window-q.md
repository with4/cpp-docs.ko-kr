---
title: 하나의 창에 하나 이상의 컨트롤을 호스팅할 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ceb9444b6371e261115bbf52ef5a249100772d1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>하나의 창에 하나 이상의 컨트롤을 호스팅할 수 있습니까?
단일 ATL 호스트 창에 하나 이상의 컨트롤을 호스트 하는 것이 불가능 합니다. 각 호스트 창 (메시지 리플렉션 및 액세스 제어 앰비언트 속성을 처리 하기 위한 간단한 메커니즘에 대 한 허용) 한 번에 정확히 하나의 컨트롤만 있을 하도록 설계 되었습니다. 그러나 사용자에 게 단일 창에서 여러 개의 컨트롤을 표시 해야 경우 해당 창의 자식 항목으로 여러 호스트 기간을 만들 수는 간단한 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)

