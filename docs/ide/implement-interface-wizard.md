---
title: 인터페이스 구현 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.interface.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf2ddf83b7a03f8d4e01b61f82e46e0d26a5547b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340543"
---
# <a name="implement-interface-wizard"></a>인터페이스 구현 마법사
COM 개체의 인터페이스를 구현합니다. 많은 인터페이스의 구현은 Visual Studio 및 Windows와 함께 사용할 수 있는 COM 라이브러리에 포함되어 있습니다. 인터페이스 구현은 해당 개체의 인스턴스를 만들고 개체에서 제공하는 서비스를 제공하는 경우 개체와 연결됩니다.  
  
 인터페이스 및 구현 설명은 Windows SDK에서 [인터페이스 및 인터페이스 구현](http://msdn.microsoft.com/library/windows/desktop/ms694356)을 참조합니다.  
  
 **구현할 인터페이스 위치**  
 인터페이스를 만들었으므로 형식 라이브러리의 위치를 지정합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**프로젝트**|형식 라이브러리는 프로젝트의 일부입니다.|  
|**Registry**|형식 라이브러리가 시스템에 등록됩니다. 등록된 형식 라이브러리는 **사용 가능한 형식 라이브러리**에 나열됩니다.|  
|**파일**|형식 라이브러리가 반드시 시스템에 등록되지는 않지만 파일에는 포함됩니다. **위치**에서 파일 위치를 제공해야 합니다.|  
  
 **사용 가능한 형식 라이브러리**  
 구현할 수 있는 인터페이스 정의가 포함된 사용 가능한 형식 라이브러리를 표시합니다. **구현할 인터페이스 위치**에서 **파일**을 클릭하면 이 상자는 변경에 사용할 수 없습니다.  
  
 **위치**  
 **사용 가능한 형식 라이브러리** 목록에서 현재 선택된 형식 라이브러리의 위치를 표시합니다. **구현할 인터페이스 위치**에서 **파일**을 선택했으면 줄임표 단추를 클릭하여 사용할 형식 라이브러리가 들어 있는 파일을 찾습니다.  
  
 **인터페이스**  
 **사용 가능한 형식 라이브러리** 상자에서 현재 선택된 형식 라이브러리에 정의가 포함된 인터페이스를 표시합니다.  
  
> [!NOTE]
>  선택한 개체에서 이미 구현한 것과 동일한 이름의 인터페이스는 **인터페이스** 상자에 표시되지 않습니다.  
  
|전송 단추|설명|  
|---------------------|-----------------|  
|**>**|**인터페이스 구현** 목록에 **인터페이스** 목록에서 현재 선택된 인터페이스 이름을 추가합니다.|  
|**>>**|**인터페이스 구현** 목록에 **인터페이스** 목록에서 사용 가능한 모든 인터페이스 이름을 추가합니다.|  
|**<**|**인터페이스 구현** 목록에서 현재 선택된 인터페이스 이름을 제거합니다.|  
|**<\<**|**인터페이스 구현** 목록에서 현재 나열된 모든 인터페이스 이름을 제거합니다.|  
  
 **인터페이스 구현**  
 개체에서 구현하기 위해 선택한 인터페이스의 이름을 표시합니다.  
  
> [!NOTE]
>  `IDispatch`에서 파생된 1 초과 인터페이스를 포함하거나 이미 다른 인터페이스에서 파생된 인터페이스를 클래스에서 구현하려고 하는 경우 COM_MAP 항목을 구분해야 합니다. 자세한 내용은 [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2)을 참조합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md)