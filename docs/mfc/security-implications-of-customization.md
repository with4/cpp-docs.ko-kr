---
title: 사용자 지정의 보안 의미 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- security, MFC Feature Pack
- MFC Feature Pack, security
ms.assetid: 9be96b12-be38-43bd-a133-5d671265f7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1416a586af479ea7b476a6c85d45992ba18873ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="security-implications-of-customization"></a>사용자 지정의 보안 의미
이 항목에서는 MFC의 잠재적인 보안 취약점에 설명 합니다.  
  
## <a name="potential-security-weakness"></a>잠재적인 보안 약점이  
 MFC 사용 하면 응용 프로그램 사용자 인터페이스 예를 들어, 단추 및 아이콘의 모양의 모양을 사용자 지정 합니다. MFC는 또한 사용자가 셸 명령을 실행 하는 사용자 지정 도구를 지원 합니다. 보안 취약점을 응용 프로그램의 사용자 지정 된 설정을 레지스트리에 사용자 프로필에 저장 되기 때문에 발생 합니다. 레지스트리에 액세스할 수 있는 사용자는 누구나 이러한 설정을 편집한 응용 프로그램 모양 또는 동작을 변경 합니다. 예를 들어 컴퓨터의 관리자는 사용자의 응용 프로그램 (에서도, 네트워크 공유) 임의의 프로그램 실행을 지정 하 여 사용자를 가장할 수 있습니다.  
  
## <a name="workarounds"></a>해결 방법  
 레지스트리에서 취약점을 이러한 세 가지 방법으로 권장 됩니다.  
  
-   저장 된 데이터 암호화  
  
-   레지스트리에서 보안 파일 대신에 데이터를 저장 합니다.  
  
     를 수행 하기 위해 이러한 처음 두 가지 방법 중 하나에서 클래스를 파생 [CSettingsStore 클래스](../mfc/reference/csettingsstore-class.md) 암호화 또는 레지스트리에 외부 저장소를 구현 하려면 해당 메서드를 재정의 합니다.  
  
-   또한 응용 프로그램에서 사용자 지정을 해제할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에 대한 사용자 지정](../mfc/customization-for-mfc.md)

