---
title: "링커 도구 경고 LNK4022 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4022
dev_langs: C++
helpviewer_keywords: LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e35974a72de349f94f2189f676b6dc955c48fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4022"></a>링커 도구 경고 LNK4022
'symbol' 기호에만 일치를 찾을 수 없습니다.  
  
 링크 또는 여러 개 찾았는데 LIB 지정된 하는 데코레이팅되지 않은 기호에 일치 하 고 모호성을 해결 하지 못했습니다. (예:.exe,.dll,.exp, 또는.lib) 출력 파일이 생성 됩니다. 이 경고 뒤 하나의 경고 [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) 각각에 대 한 기호를 복제 하 고 마지막으로 심각한 오류 옵니다 [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)합니다.  
  
 이 경고를 방지 하려면 데코레이팅된 형식으로 기호를 지정 합니다. 실행 [DUMPBIN](../../build/reference/dumpbin-options.md) 개체에서 참조를 데코 레이트 된 이름입니다.