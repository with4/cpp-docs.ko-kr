---
title: "링커 도구 경고 LNK4037 | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4037
dev_langs: C++
helpviewer_keywords: LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c93eab2faf81e4cd743eae4befa2f842c100589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4037"></a>링커 도구 경고 LNK4037

>'*기호*'가 없습니다; 무시 됩니다.

데코 레이트 된 이름을 *기호* 를 사용 하 여 정렬할 수 없습니다는 [/순서](../../build/reference/order-put-functions-in-order.md) 프로그램에 없기 때문에 옵션입니다. 사양을 확인 *기호* 순서 지시 파일에 있습니다. 자세한 내용은 참조는 [/ORDER (순서로 Put 함수)](../../build/reference/order-put-functions-in-order.md) 링커 옵션입니다.

> [!NOTE]
> 링크 정적 함수 이름이 공용 기호 이름이 없기 때문에 정적 함수 순서 수 없습니다. 때 **/순서** 지정 하면이 링커 경고 정적 순서 응답 파일에서 각 기호에 대해 생성 되었거나 찾을 수 없습니다.