---
title: AtlAxWinInit 호출 해야 하는 경우는 합니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9aa1dd14ccae555d4ab9acbbac15e9b66cafe6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit 호출 해야 하는 경우는 합니까?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 등록는 **"AtlAxWin80"** 호스트 창을 만들 하려고 하기 전에이 함수를 호출 해야 하므로 창 클래스 (더하기 몇 가지 사용자 지정 창 메시지). 그러나 Api (및 사용 하는 클래스)을 호스팅하는 이후이 함수를 명시적으로 호출할 필요가 항상 종종를이 함수를 호출 합니다. 이 함수를 두 번 이상 호출에 나쁜 영향을 미치지 않습니다. 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 AtlAxWinTerm 호출 해야 하는 경우는 합니까     
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)
