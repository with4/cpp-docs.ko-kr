---
title: 일반 클래스 디자인 원칙 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b2d0915c4b2940e93b781e7a56e2640c64a7f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="general-class-design-philosophy"></a>일반 클래스 디자인 원칙
Microsoft Windows는 c + + 언어 유행 훨씬 전에 설계 되었습니다. 응용 프로그램 C 언어 Windows 응용 프로그램 프로그래밍 인터페이스 (API)를 사용 하므로 해당 인터페이스 장래에 유지 됩니다. 따라서 모든 c + + Windows 인터페이스를 설명 하는 절차는 C 언어 API를 기반으로 빌드해야 합니다. 이 c + + 응용 프로그램 C 응용 프로그램과 함께 사용할 수 있는지를 보장 합니다.  
  
 Microsoft Foundation Class 라이브러리는 다음과 같은 설계 목표를 충족 하는 Windows에 대 한 개체 지향 인터페이스.  
  
-   Windows 용 응용 프로그램을 작성 하는 데에서 상당히 줄어듭니다.  
  
-   실행 속도 C 언어 API와 유사 합니다.  
  
-   최소 코드 크기 오버 헤드가 발생 합니다.  
  
-   모든 Windows C 함수를 직접 호출할 수 있습니다.  
  
-   C + +에 기존 C 응용 프로그램으로 더 쉽게 변환 됩니다.  
  
-   C 언어 Windows 프로그래밍 경험의 기존 베이스에서 활용할 수 있습니다.  
  
-   3. 보다 c + +를 사용 하 여 Windows API 쉽게 사용할 수 있도록  
  
-   ActiveX 컨트롤, 데이터베이스 지원, 인쇄, 도구 모음 및 상태 표시줄 등의 기능을 사용 하 여 할 수 있지만의 강력한 추상화 쉽게 복잡합니다.  
  
-   C + + 언어 기능을 효과적으로 사용 하는 c + +에 대 한 Windows API true입니다.  
  
 MFC 라이브러리의 디자인에 대 한 자세한, 참조:  
  
-   [응용 프로그램 프레임 워크](../mfc/application-framework.md)  
  
-   [C 언어 API와의 관계](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

