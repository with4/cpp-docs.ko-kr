---
title: "링커 도구 오류 LNK2013 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2013
dev_langs: C++
helpviewer_keywords: LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cf88f768f05eee06ae8ffaa66f8de5a9c443f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2013"></a>링커 도구 오류 LNK2013
픽스업 형식 픽스업 오버플로입니다. 대상 'symbol name' 범위를 벗어났습니다.  
  
 맞출 수 없습니다 필요한 주소 또는 오프셋 지정 된 명령에 대상 기호가 너무 멀리 떨어져 명령 위치에서 있으므로 합니다.  
  
 여러 이미지를 만들거나 사용 하 여이 문제를 해결할 수는 [/순서](../../build/reference/order-put-functions-in-order.md) 명령과 대상을 좀 더 근접 옵션입니다.  
  
 기호 이름이 사용자 정의 기호 (및 컴파일러에서 생성 된 기호가 아닌) 인 오류를 해결 하려면 다음 작업 시도해 볼 수 있습니다.  
  
-   Static이 아닌 정적 함수를 변경 합니다.  
  
-   호출자와 동일 하 게 정적 함수를 포함 하는 코드 섹션을 이름을 바꿉니다.  
  
 사용 하 여 `DUMPBIN /SYMBOLS`함수 정적 인지, 합니다.