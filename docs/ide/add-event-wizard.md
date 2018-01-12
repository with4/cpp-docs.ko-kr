---
title: "이벤트 추가 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.event.overview
dev_langs: C++
helpviewer_keywords: Add Event Wizard [C++]
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 62ecbe7dece323ce5e99fbe32b3b936fe3661362
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="add-event-wizard"></a>이벤트 추가 마법사
이 마법사는 MFC ActiveX 컨트롤 프로젝트에는 이벤트를 추가합니다. 사용자 지정 이벤트를 지정할 수 있습니다, 일반적으로 스톡 이벤트를 사용자 지정할 수 있습니다 또는 스톡 이벤트 목록에서 선택할 수 있습니다.  
  
 **이벤트 이름**  
 자동화 클라이언트는 클래스에서 이벤트를 요청 하는 데 사용 하는 이름을 설정 합니다. 이름을 입력 하거나 목록에서 선택 합니다.  
  
 **이벤트 유형**  
 추가할 이벤트의 유형을 나타냅니다. 선택 하는 경우에 사용할 수는 **이벤트 이름** 목록입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**재고**|있는지 스톡 이벤트 단추 클릭과 같은 구현 될이 클래스를 지정 합니다. 스톡 이벤트는 Microsoft Foundation 클래스 (MFC) 라이브러리에 정의 됩니다.|  
|**사용자 지정**|이벤트의 사용자 지정 구현을 제공 하는 것을 지정 합니다.|  
  
 **내부 이름**  
 이벤트를 보내는 멤버 함수 이름을 설정 합니다. 사용자 지정 이벤트에 대해서만 사용할 수 있습니다. 이름은 기반 **이벤트 이름**합니다. 과 다른 이름을 제공 하려는 경우 내부 이름을 변경할 수 있습니다 **이벤트 이름**합니다.  
  
 **매개 변수 형식**  
 형식이 설정 된 **매개 변수 이름**합니다. 목록에서 유형을 선택 합니다.  
  
 **매개 변수 이름**  
 이벤트를 통과 하는 매개 변수 이름을 설정 합니다. 이름을 입력 한 다음 클릭 해야 **추가** 매개 변수 목록을 추가 합니다.  
  
 클릭 한 후 **추가**, 매개 변수 이름에 표시 **매개 변수 목록**합니다.  
  
> [!NOTE]
>  매개 변수 이름을 입력 한 다음 클릭 **마침** 클릭 하기 전에 **추가**, 다음 매개 변수는 이벤트에 추가 되지 않습니다. 메서드를 찾아 수동으로 매개 변수를 삽입 해야 합니다. **매개 변수 목록**  
  
 **추가**  
 지정한 매개 변수를 추가 **매개 변수 이름**, 및 해당 형식에 **매개 변수 목록**합니다. 클릭 해야 **추가** 매개 변수를 목록에 있습니다.  
  
 **제거**  
 선택한 매개 변수 제거 **매개 변수 목록** 목록에서 합니다.  
  
 **매개 변수 목록**  
 모든 매개 변수 및 메서드에 대 한 현재 추가 된 개체 유형을 표시 합니다. 매개 변수를 추가 하면 마법사가 업데이트 **매개 변수 목록** 각 매개 변수 형식으로 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트 추가](../ide/adding-an-event-visual-cpp.md)