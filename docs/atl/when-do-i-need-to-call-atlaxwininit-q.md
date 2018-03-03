---
title: "AtlAxWinInit 호출 해야 하는 경우는 합니까? | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69dfcfbe0c8c05d275a5f3a8f86c30b0e59bd3a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit 호출 해야 하는 경우는 합니까?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 등록는 **"AtlAxWin80"** 호스트 창을 만들 하려고 하기 전에이 함수를 호출 해야 하므로 창 클래스 (더하기 몇 가지 사용자 지정 창 메시지). 그러나 Api (및 사용 하는 클래스)을 호스팅하는 이후이 함수를 명시적으로 호출할 필요가 항상 종종를이 함수를 호출 합니다. 이 함수를 두 번 이상 호출에 나쁜 영향을 미치지 않습니다. 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 AtlAxWinTerm 호출 해야 하는 경우는 합니까     
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)
