---
title: "명령 개체 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d83f0a14562985386f0f1f75cfcd99518fea6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-object-interfaces"></a>명령 개체 인터페이스
사용 하 여 명령 개체는 `IAccessor` 매개 변수 바인딩을 지정 하는 인터페이스입니다. 소비자 호출 `IAccessor::CreateAccessor`, 배열을 전달 `DBBINDING` 구조입니다. `DBBINDING`열 바인딩 (예: 형식 및 길이)에 대 한 정보를 포함합니다. 공급자는 구조를 받아 변환이 필요한 지 여부 및 데이터를 전송 하는 방법을 결정 합니다.  
  
 `ICommandText` 인터페이스는 텍스트 명령을 지정 하는 방법을 제공 합니다. `ICommandProperties` 인터페이스는 모든 명령 속성을 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)