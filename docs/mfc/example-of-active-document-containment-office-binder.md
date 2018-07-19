---
title: '액티브 문서 포함의 예: Office Binder | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e4f82840a4c5620762ad57b5b9fa8dd7e62d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345963"
---
# <a name="example-of-active-document-containment-office-binder"></a>액티브 문서 포함의 예: Office Binder
Microsoft Office Binder는 액티브 문서 컨테이너의 예시입니다. Office Binder 컨테이너가 않는 일반적으로 두 개의 주 창이 포함 됩니다. 왼쪽된 창에 바인더의 액티브 문서에 해당 하는 아이콘이 포함 되어 있습니다. 각 문서 라고는 *섹션* 바인더 내에서. 예를 들어 한 바인더는 Word 문서, PowerPoint 파일, Excel 스프레드시트, 및 등을 포함할 수 있습니다.  
  
 왼쪽된 창에서 아이콘을 클릭 하면 해당 활성 문서를 활성화 합니다. 바인더의 오른쪽 창에는 다음 현재 선택 된 활성 문서의 내용을 표시합니다.  
  
 열고 바인더에서 Word 문서를 활성화 하는 경우 Word 메뉴 모음 및 도구 모음 보기 프레임의 위쪽에 나타나고 모든 단어 명령이 나 도구를 사용 하 여 문서의 내용을 편집할 수 있습니다. 그러나 메뉴 모음 바인더의와 Word의 메뉴 모음의 조합입니다. 바인더과 Word 없으므로 **도움말** 메뉴, 각 메뉴의 내용을 병합 됩니다. Office Binder와 같은 액티브 문서 컨테이너를 자동으로 제공 **도움말** 메뉴 병합; 자세한 내용은 참조 [도움말 메뉴 병합](../mfc/help-menu-merging.md)합니다.  
  
 현재 문서의 응용 프로그램 종류의 수용 하기 위한 바인더의 인터페이스 변경 다른 응용 프로그램 종류의 액티브 문서는 선택 합니다. 예를 들어 한 바인더 Excel 스프레드시트를 포함 하는 경우 바인더에서 메뉴는 Excel 스프레드시트 섹션을 선택 하면 변경를 볼 수 있습니다.  
  
 형식은, 물론, 다른 가능한 바인더 옆에 있는 컨테이너입니다. 파일 탐색기의 왼쪽된 창 오른쪽 창에서 현재 선택 된 디렉터리에 포함 된 파일을 표시 하는 동안 드라이브 또는 네트워크 디렉터리의 계층적 목록을 표시 하려면 트리 컨트롤을 사용 하는 일반적인 이중 창 인터페이스를 사용 합니다. 이중 창 인터페이스를 사용 하는 것이 아니라 컨테이너 (예: Microsoft Internet Explorer), 인터넷 브라우저 종류는 일반적으로 단일 프레임 있으며 하이퍼링크를 사용 하 여 탐색을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [활성 문서 포함](../mfc/active-document-containment.md)

