---
title: "연결 지점 구현 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.cp.overview
dev_langs: C++
helpviewer_keywords: Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f29b4f25d937c2f538373ff85819f7315150e712
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implement-connection-point-wizard"></a>연결 지점 구현 마법사
이 마법사는 COM 개체에 대 한 연결 지점을 구현합니다. 연결 가능 개체 (즉, 원본) 한 연결 지점을 자체 인터페이스에 대 한 모든 보내기 인터페이스를 노출할 수 있습니다. Visual c + +와 Windows 모두 나가는 인터페이스가 있는 형식 라이브러리를 제공 합니다. 클라이언트에서는 개체 (싱크)에 대해 각 송신 인터페이스를 구현할 수 있습니다.  
  
 자세한 내용은 참조 [ATL 연결 지점](../atl/atl-connection-points.md)합니다.  
  
 **사용 가능한 형식 라이브러리**  
 연결 지점을 구현할 수 있는 인터페이스 정의가 포함 된 사용 가능한 형식 라이브러리를 표시 합니다. 형식 라이브러리를 사용 하 여 포함 된 파일을 찾기 위해 줄임표 단추를 클릭 합니다.  
  
 **위치**  
 현재 선택 된 형식 라이브러리의 위치를 표시는 **사용 가능한 형식 라이브러리** 목록입니다.  
  
 **인터페이스**  
 현재 선택 된 형식 라이브러리에 해당 정의가 포함 된 인터페이스를 표시는 **사용 가능한 형식 라이브러리** 상자입니다.  
  
|전송 단추|설명|  
|---------------------|-----------------|  
|**>**|에 추가 **연결 지점을 구현** 에서 현재 선택 된 인터페이스 이름 목록에서 **인터페이스** 목록입니다.|  
|**>>**|에 추가 된 **연결 지점을 구현** 에서 사용할 수 있는 모든 인터페이스 이름 목록을 **인터페이스** 목록입니다.|  
|**<**|현재 선택 된 인터페이스 이름을 제거는 **연결 지점을 구현** 목록입니다.|  
|**<<**|인터페이스에 현재 표시 되어 이름을 모두 제거는 **연결 지점을 구현** 목록입니다.|  
  
 **연결 지점 구현**  
 클릭할 때 연결 지점을 구현 하는 인터페이스의 이름을 표시 **마침**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점 구현](../ide/implementing-a-connection-point-visual-cpp.md)