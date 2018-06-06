---
title: 연결 지점 구현 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.cp.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef2f7efa92de3714170e403ea50b5f486c8367d6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33323760"
---
# <a name="implement-connection-point-wizard"></a>연결 지점 구현 마법사
이 마법사는 COM 개체의 연결 지점을 구현합니다. 연결 가능한 개체(즉, 원본)는 자체 인터페이스 또는 모든 송신 인터페이스에 대한 연결 지점을 노출할 수 있습니다. Visual C++ 및 Windows는 모두 송신 인터페이스가 있는 형식 라이브러리를 제공합니다. 각 송신 인터페이스는 클라이언트가 개체(예: 싱크)에 구현할 수 있습니다.  
  
 자세한 내용은 [ATL 연결 지점](../atl/atl-connection-points.md)을 참조하세요.  
  
 **사용 가능한 형식 라이브러리**  
 연결 지점을 구현할 수 있는 인터페이스 정의가 포함된 사용 가능한 형식 라이브러리를 표시합니다. 줄임표 단추를 클릭하여 사용할 형식 라이브러리가 들어 있는 파일을 찾습니다.  
  
 **위치**  
 **사용 가능한 형식 라이브러리** 목록에서 현재 선택된 형식 라이브러리의 위치를 표시합니다.  
  
 **인터페이스**  
 **사용 가능한 형식 라이브러리** 상자에서 현재 선택된 형식 라이브러리에 정의가 포함된 인터페이스를 표시합니다.  
  
|전송 단추|설명|  
|---------------------|-----------------|  
|**>**|**인터페이스** 목록에서 현재 선택된 인터페이스 이름을 **연결 지점 구현** 목록에 추가합니다.|  
|**>>**|**인터페이스** 목록에서 사용 가능한 모든 인터페이스 이름을 **연결 지점 구현** 목록에 추가합니다.|  
|**<**|**연결 지점 구현** 목록에서 현재 선택된 인터페이스 이름을 제거합니다.|  
|**<<**|**연결 지점 구현** 목록에서 현재 나열된 모든 인터페이스 이름을 제거합니다.|  
  
 **연결 지점 구현**  
 **마침**을 클릭하면 연결 지점을 구현할 인터페이스의 이름이 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점 구현](../ide/implementing-a-connection-point-visual-cpp.md)