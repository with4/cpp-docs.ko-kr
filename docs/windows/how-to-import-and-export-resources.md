---
title: "방법: 리소스 가져오기 및 내보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21f596996d090d9d41146c6f8ea9cb24884dd4c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-import-and-export-resources"></a>방법: 리소스 가져오기 및 내보내기
Visual C++에서 사용하도록 그래픽 리소스(비트맵, 아이콘, 커서 및 도구 모음), HTML 파일 및 사용자 지정 리소스를 가져올 수 있습니다. Visual C++ 프로젝트에서 동일한 형식의 파일을 개발 환경 외부에서 사용할 수 있는 별도의 파일로 내보낼 수 있습니다.  
  
> [!NOTE]
>  액셀러레이터 키, 대화 상자 및 문자열 테이블과 같은 리소스 종류는 독립 실행형 파일 형식이 아니므로 가져오거나 내보낼 수 없습니다.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>현재 리소스 파일로 개별 리소스를 가져오려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md), 리소스 스크립트에 대 한 노드를 마우스 오른쪽 단추로 클릭 (*.rc) 리소스를 추가할 파일입니다.  
  
2.  클릭 **가져오기** 바로 가기 메뉴.  
  
3.  비트맵(.bmp), 아이콘(.ico), 커서(.cur), Html 파일(.htm) 또는 기타 가져오려는 파일의 파일 이름을 찾아 선택합니다.  
  
4.  클릭 **확인** 에서 선택한 파일에 리소스를 추가할 **리소스** 보기.  
  
    > [!NOTE]
    >  가져오기 프로세스는 선택한 특정 리소스 종류에 관계없이 동일한 방식으로 작동합니다. 가져온 리소스는 해당 리소스 종류에 적합한 노드에 자동으로 추가됩니다.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>Visual C++ 외부에서 사용하도록 비트맵, 아이콘 또는 커서를 별도의 파일로 내보내려면  
  
1.  **리소스** 보기에서 내보낼 리소스를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  클릭 **내보내기** 바로 가기 메뉴.  
  
3.  에 **리소스 내보내기** 대화 상자, 현재 파일 이름을 적용 하거나 새 이름을 입력 합니다.  
  
4.  폴더로 이동 하 여 파일을 저장 하 고 클릭 하려는 **내보내기**합니다.  
  

  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)