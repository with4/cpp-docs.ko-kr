---
title: "ODBC 클래스와 스레드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d1d922dfc34fa3e5530eca77a6501ad3e331fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-classes-and-threads"></a>ODBC 클래스와 스레드
MFC 4.2 부터는 지원은 다중 스레드 MFC ODBC 클래스에 대 한 합니다. 그러나 단, MFC 지원 하지 않는 다중 스레딩 DAO 클래스에 대 한 합니다.  
  
 ODBC 클래스에 대 한 다중 스레딩 지원에는 몇 가지 제한 사항이 있습니다. 이러한 클래스는 ODBC API를 때문에 다중 스레딩 지원 작성 된 구성 요소의 제한 됩니다. 예를 들어 대부분의 ODBC 드라이버는 스레드로부터 안전; 하지 따라서 MFC ODBC 클래스 이러한 견인차 중 하나를 사용 하는 경우 스레드로부터 안전 하지 않습니다. 특정 드라이버 스레드로부터 안전 하 게 보호 되는지 확인 해야 합니다.  
  
 다중 스레드 응용 프로그램을 만들 때 여러 스레드를 사용 하 여 동일한 개체를 조작 하기 위한 매우 주의 해야 합니다. 예를 들어 동일한를 사용 하 여 `CRecordset` 두 스레드에서 개체 데이터를 검색할 때 문제가 발생할 수 있습니다; 한 스레드에 인출 작업이 다른 스레드에서 인출 된 데이터를 덮어쓸 수 있습니다. 열려 있는 공유 하는 별도의 스레드에서 MFC ODBC 클래스의 보다 일반적인 사용입니다 `CDatabase` 별도의 같은 ODBC 연결을 사용 하는 스레드 간에 개체 `CRecordset` 각 스레드에 개체입니다. 열려 있지 않은 전달 하지 않아야 참고 `CDatabase` 개체는 `CRecordset` 다른 스레드의 개체입니다.  
  
> [!NOTE]
>  여러 스레드가 동일한 개체를 조작 해야 할 경우 중요 한 섹션과 같은 적절 한 동기화 메커니즘을 구현 해야 합니다. 주의 특정 작업을와 같은 **열려**, 보호 되지 않습니다. 이러한 작업 호출 되지 것입니다 동시에 별도 스레드에서 있을 수 있습니다.  
  
 다중 스레드 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 [다중 스레딩 항목](../../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [데이터 액세스 프로그래밍 (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)