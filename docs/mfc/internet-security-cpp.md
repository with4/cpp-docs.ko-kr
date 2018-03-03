---
title: "인터넷 보안 (c + +) | Microsoft Docs"
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
- code signing [MFC], Internet security
- sandboxing [MFC]
- digital signatures [MFC], Internet security
- code signing [MFC]
- Web application security [MFC]
- code access security [MFC], Internet security considerations
- security [MFC]
- security [MFC], Internet
- Internet applications [MFC], security
- Web application security [MFC], Internet security approaches
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a44e528e871d784c432730799c44ac91af465be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="internet-security-c"></a>인터넷 보안(C++)
코드 보안은 인터넷 응용 프로그램의 사용자와 개발자를 위한 중요 한 문제입니다. 위험이 있는: 악의적인 코드, 변조 되었거나, 코드 및 작성자 또는 알 수 없는 사이트에서 코드입니다.  
  
 인터넷에 대 한 개발 하는 경우 두 가지 기본 보안 방법에 있습니다. 첫 번째 "샌드박스" 라고 합니다. 이 방법에서는 응용 프로그램, Api의 특정 집합으로 제한 하 고 프로그램 사용자의 컴퓨터에 데이터를 손상 될 수 있습니다 파일 I/O와 같은 잠재적으로 위험한 것에서 제외 됩니다. 두 번째 디지털 서명을 사용 하 여 구현 됩니다. 이 방법은 라고 "shrinkwrap" 인터넷에 대 한 합니다. 코드를 확인 하 고 개인 키/공개 키 기술을 사용 하 여 서명 합니다. 코드를 실행 하기 전에 알려진된 인증 된 소스에서 코드를 하 고 코드 서명 된 이후 변경 되지 않은 해당 디지털 서명을 확인 합니다.  
  
 첫 번째 경우에서 응용 프로그램에 나쁜 영향을 미치지 수행 되지 것입니다 및 응용 프로그램의 출처를 신뢰할 신뢰 합니다. 두 번째 디지털 서명에 신뢰성 확인을 위해 사용 됩니다. 디지털 서명을 확인 하 고 코드의 게시자에 대 한 세부 정보를 제공 하는 데 사용 하는 산업 표준입니다. 기술은 RSA 등 X.509 표준을 기반으로 합니다. 브라우저는 일반적으로 사용자가을 원하는 경우 다운로드 한 출처를 알 수 없는 코드의 실행을 선택할 수 있습니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

