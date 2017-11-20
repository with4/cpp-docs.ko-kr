---
title: "원격 자동화의 기능은 무엇입니까? | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6766b2fcc5d277b86f979252bf22e6ae343e608e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="what-does-remote-automation-provide"></a>원격 자동화의 기능은 무엇입니까?
원격 자동화를 사용하면 프로그램은 다른 한 컴퓨터에서 `IDispatch` 구현을 호출할 수 있습니다. 또한 구체적으로, 자동화가 필요한 다른 인터페이스를 지원 **IEnumVARIANT** 컬렉션 지원에 대 한 합니다. 다른 COM 인터페이스를 배포 하는 기능은 제공 하지 않습니다 (제외 하 고 **IUnknown**, 물론) 및 일반적인 자동화와 같이 자동화에 의해 지원 되는 데이터 형식에 대 한 마샬링 지원 포함 합니다.  
  
 이 기능 집합을 통해 프로그램에서는 액세스 가능 네트워크 노드에서 실행 중인 개체의 메서드와 속성(컬렉션 또는 추가 자동화 개체를 반환하는 메서드 및 속성 포함)에 액세스할 수 있습니다. 클라이언트 시스템이 적절한 소프트웨어를 실행하는 경우 서버가 자동화 기능을 다시 사용하여 클라이언트로 콜백할 수 있습니다. 이 작업은 32비트 및 64비트 클라이언트 전용이며 동일한 메커니즘을 사용하지 않지만 개념적으로 이벤트와 비슷합니다.  
  
 원격 자동화 서버로 작동할 수 있는 응용 프로그램의 경우 실행 서버로 구현되어야 합니다(즉, "inproc 서버"가 아닌 "로컬 서버").  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화가 필요한 경우 있습니까](where-does-remote-automation-fit-in-q.md)   
 [DCOM의 역사](../mfc/history-of-dcom.md)
