---
title: "저장 프로시저 하나에서 여러 결과 집합을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 787c2123981f894eb4b6ba088cfcef774b6ed6f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>저장 프로시저 하나에서 여러 결과 집합 사용
대부분의 저장된 프로시저는 여러 결과 집합을 반환 합니다. 이상의 select 문 또는 일반적으로 이러한 저장된 프로시저는 하나 포함 됩니다. 소비자는 모든 결과 집합을 처리 하기 위해이 고려해 야 합니다.  
  
### <a name="to-handle-multiple-result-sets"></a>집합을 여러 결과 처리 하려면  
  
1.  만들기는 `CCommand` 클래스와 `CMultipleResults` 템플릿 인수로 및 선택한 접근자와 함께 합니다. 일반적으로 동적 자동 또는 수동 접근자입니다. 다른 유형의 접근자를 사용 하는 경우 각 행 집합에 대 한 출력 열을 확인 수 수 없습니다.  
  
2.  평소와 같이 저장된 프로시저를 실행 하 고 열을 바인딩합니다 (참조 [데이터 인출?](../../data/oledb/fetching-data.md)).  
  
3.  데이터를 사용 합니다.  
  
4.  호출 `GetNextResult` 에 `CCommand` 클래스입니다. 다른 결과 행 집합을 사용할 수 있으면 `GetNextResult` S_OK를 반환 하 고 수동 접근자를 사용 하는 경우 열을 다시 바인딩해야 합니다. 경우 `GetNextResult` 에서 오류를 반환 결과 집합이 더 이상 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)