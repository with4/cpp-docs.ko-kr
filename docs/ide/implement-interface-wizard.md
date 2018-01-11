---
title: "인터페이스 구현 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.interface.overview
dev_langs: C++
helpviewer_keywords: Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d224546eb8bb06421c2e84206e1f4d4dc77f9668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implement-interface-wizard"></a>인터페이스 구현 마법사
이 마법사는 COM 개체에 대 한 인터페이스를 구현합니다. 여러 인터페이스의 구현은 Visual Studio 및 Windows에 사용할 수 있는 COM 라이브러리에 포함 됩니다. 해당 개체의 인스턴스를 만들고 개체에서 제공 하는 서비스를 제공 하는 경우 인터페이스를 구현할 때 개체와 연결 됩니다.  
  
 인터페이스와 구현을의 논의 알려면 [인터페이스와 인터페이스 구현을](http://msdn.microsoft.com/library/windows/desktop/ms694356) Windows sdk에서입니다.  
  
 **구현할 인터페이스**  
 인터페이스를 만들었으므로 형식 라이브러리의 위치를 지정 합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**프로젝트**|형식 라이브러리에는 프로젝트의 일부입니다.|  
|**Registry**|형식 라이브러리가 시스템에 등록 되어 있습니다. 등록 된 형식 라이브러리에 나열 된 **사용 가능한 형식 라이브러리**합니다.|  
|**파일**|형식 라이브러리가 시스템에 등록 되지 않았습니다 하지만 파일에 포함 합니다. 파일 위치를 제공 해야 **위치**합니다.|  
  
 **사용 가능한 형식 라이브러리**  
 구현할 수 있는 인터페이스 정의가 포함 된 사용 가능한 형식 라이브러리를 표시 합니다. 클릭 하면 **파일** 아래 **구현할 인터페이스**,이 상자는 변경할 수 없습니다.  
  
 **위치**  
 현재 선택 된 형식 라이브러리의 위치를 표시는 **사용 가능한 형식 라이브러리** 목록입니다. 선택한 경우 **파일** 아래 **구현할 인터페이스**, 형식 라이브러리를 사용 하 여 포함 된 파일을 찾기 위해 줄임표 단추를 클릭 합니다.  
  
 **인터페이스**  
 현재 선택 된 형식 라이브러리에 해당 정의가 포함 된 인터페이스를 표시는 **사용 가능한 형식 라이브러리** 상자입니다.  
  
> [!NOTE]
>  선택한 개체에 의해 이미 구현 된에 표시 되지 않는 동일한 이름을 가진 인터페이스는 **인터페이스** 상자입니다.  
  
|전송 단추|설명|  
|---------------------|-----------------|  
|**>**|에 추가 **인터페이스를 구현** 목록에서 현재 선택 된 인터페이스 이름은 **인터페이스** 목록입니다.|  
|**>>**|에 추가 된 **인터페이스를 구현** 에서 사용할 수 있는 모든 인터페이스 이름 목록을 **인터페이스** 목록입니다.|  
|**<**|현재 선택 된 인터페이스 이름을 제거는 **인터페이스를 구현** 목록입니다.|  
|**<\<**|인터페이스에 현재 표시 되어 이름을 모두 제거는 **인터페이스를 구현** 목록입니다.|  
  
 **인터페이스 구현**  
 선택한 개체에 구현 하는 인터페이스의 이름을 표시 합니다.  
  
> [!NOTE]
>  파생 된 둘 이상의 인터페이스를 포함 하는 경우 `IDispatch`, 또는 클래스에 이미 다른 인터페이스에서 파생 된 인터페이스를 구현 하려고 하는 경우 다음 COM_MAP 엔트리를 명확 하 게 해야 합니다. 참조 [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md)