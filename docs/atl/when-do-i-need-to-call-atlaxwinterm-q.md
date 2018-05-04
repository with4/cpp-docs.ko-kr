---
title: AtlAxWinTerm 호출 해야 하는 경우는 합니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinTerm
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61830023d3fb67d331784769f32cda4eee8355b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>AtlAxWinTerm 호출 해야 하는 경우는 합니까?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) 등록 취소는 **"AtlAxWin80"** 창 클래스입니다. 이 함수 (경우에 호출 해야 호스트 창을 만들 더 이상 필요) 모든 기존 호스트 창을 소멸 된 후입니다. 이 함수를 호출 하지 않으면, 창 클래스는 등록을 취소할 자동으로 프로세스가 종료 될 때입니다.  
  
## <a name="see-also"></a>참고 항목  
 AtlAxWinInit 호출 해야 하는 경우는 합니까  
[컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)

