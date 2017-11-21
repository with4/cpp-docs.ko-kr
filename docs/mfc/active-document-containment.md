---
title: "액티브 문서 포함 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 749d4badb3a7b5a2c61fa753a840765f14e2a329
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="active-document-containment"></a>액티브 문서 포함
액티브 문서 포함은 작업을 만들고 각 문서 유형에 대 한 여러 응용 프로그램 프레임을 사용 하도록 요구 하는 대신 문서는 단일 한 프레임을 제공 하는 기술입니다. OLE 콘텐츠의 일부만 활성화 될 수 있는 복합 문서 내에서 포함 된 개체와 함께 작동 한다는 점에서 기본 OLE 기술에서 다릅니다. 액티브 문서 포함을 단일 프레임의 컨텍스트 내에서 전체 문서 (즉, 전체 응용 프로그램, 연결 된 메뉴, 도구 모음, 및 등을 포함 하 여)를 활성화 합니다.  
  
 액티브 문서 포함 기술 Office Binder를 구현 하는 Microsoft Office에 대 한 원래 개발 되었습니다. 그러나 Office Binder 이외의 액티브 문서 컨테이너를 지원할 수 있을 정도로 유연 기술과 Office 및 Office 호환 응용 프로그램 이외의 문서 서버를 지원할 수 있습니다.  
  
 활성 문서를 호스팅하는 응용 프로그램에서 호출 되는 [액티브 문서 컨테이너](../mfc/active-document-containers.md)합니다. 이러한 컨테이너에는 Microsoft Office Binder 또는 Microsoft Internet Explorer이 있습니다.  
  
 액티브 문서 포함 ole 확장 프로그램 집합이 문서 OLE의 복합 문서 기술을 구현 됩니다. 확장은 포함 된 콘텐츠는 단일 않고 전체 문서를 나타내기 위해 포함 가능한 경량, 내부 개체를 허용 하는 추가 인터페이스입니다. OLE 문서와 마찬가지로 액티브 문서 포함 액티브 문서 및 액티브 문서 자체에 대 한 사용자 인터페이스 및 조작 기능을 제공 하는 서버에 대 한 표시 공간을 제공 하는 컨테이너를 사용 합니다.  
  
 [액티브 문서 서버](../mfc/active-document-servers.md) 는 지 원하는 하나 이상의 액티브 문서 클래스 (예: Word, Excel 또는 PowerPoint) 응용 프로그램 자체 각 개체가 개체에서 활성화할 수를 허용 하는 확장 프로그램 인터페이스를 지원 하는 위치는 적합 한 컨테이너입니다.  
  
 [액티브 문서](../mfc/active-documents.md) (Word, Excel 등과 같은 액티브 문서 서버에서 제공) 기본적으로 전체 수행 되는 기존 있는 문서는 다른 액티브 문서 컨테이너 내에서 개체도 포함 됩니다. 포함 된 개체와 달리 액티브 문서 페이지를 완전히 제어할 있고 (모든 기본 명령 및 도구)와 응용 프로그램의 전체 인터페이스를 사용자를 편집할 수 있습니다.  
  
 액티브 문서는 표준 OLE 포함된 개체에서 구분 하 여 가장 인식 됩니다. OLE 규칙 포함된 된 개체를 소유 하는 문서의 페이지 내에서 표시 되는 하나 이며 OLE 컨테이너에 의해 관리 되는 문서. 컨테이너 문서의 나머지 부분을 사용 하 여 포함 된 개체의 데이터를 저장합니다. 그러나 표시 하는 페이지 제어 하지 않는 한다는 점에서 포함 된 개체 제한 됩니다.  
  
 액티브 문서 컨테이너 응용 프로그램의 사용자 (Office Binder의 섹션 이라고 함)는 활성 문서를 만들 수 있습니다 (이러한 응용 프로그램은 사용 하도록 설정 하는 액티브 문서) 제공는 원하는 응용 프로그램을 사용 하 여, 사용자가 결과 프로젝트를 관리할 수 있지만 한 인쇄 하 고 등 고유 하 게 이름을 지정할 수 있는 저장. 동일한 방법으로 인터넷 브라우저의 사용자가 로컬 파일 시스템 뿐만 아니라 전체 네트워크 단일 위치에서 해당 저장소에서 문서를 찾아볼 수 있는 기능을 단일 문서 저장소 개체인 것 처럼 처리할 수 있습니다.  
  
## <a name="sample-programs"></a>샘플 프로그램  
  
-   [MFCBIND](../visual-cpp-samples.md) 샘플 액티브 문서 컨테이너 응용 프로그램의 구현을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC COM](../mfc/mfc-com.md)

