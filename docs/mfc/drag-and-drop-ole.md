---
title: 끌어서 놓기 (OLE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc23c7695bf5afa22734c382ddc72e8418ff74c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="drag-and-drop-ole"></a>끌어서 놓기(OLE)
Ole 끌어서 놓기 기능은 주로 데이터 복사 및 붙여넣기의 바로 가기를 표시 합니다. 클립보드를 사용 하 여 복사 하거나 데이터를 붙여 넣을 때 몇 가지 단계는 필요 합니다. 데이터 선택를 클릭 **잘라내기** 또는 **복사** 에서 **편집** 대상 파일, 창 또는 응용 프로그램로 이동 메뉴 누른 원하는 위치에 커서를 놓고 **붙여넣기** 에서 **편집** 메뉴.  
  
 OLE 끌어서 놓기 파일 이름을 처리할 수 있으며 응용 프로그램에 파일 이름을 전달 특별히 디자인 된 파일 관리자 끌어서 놓기 메커니즘에서 차이가 있습니다. OLE 끌어서 놓기 훨씬 더 일반적입니다. 에 끌어 놓는 모든 데이터를 클립보드에 배치 될 수도 있습니다.  
  
 OLE 끌어서 놓기를 사용 하면 프로세스에서 두 단계를 제거 합니다. 있습니다 ("놓기 소스")의 소스 창에서 데이터를 선택, 필요한 대상 ("놓기 대상")에 끌어서 마우스 단추에서 손을 떼기 여 삭제 합니다. 작업 메뉴에 대 한 필요성 제거 하 고 복사/붙여넣기 작업 보다 빠릅니다. 유일한 요구 사항은 이어야 한다는 것뿐입니다 놓기 소스와 대상 놓기 열려 있고 화면에서 적어도 부분적으로 표시 합니다.  
  
 OLE 끌어서 놓기를 사용 하 여 데이터 전송할 수 있습니다 한 위치에서 서로 다른 문서 또는 응용 프로그램 간에 문서 내의 다른 합니다. 컨테이너 또는 서버 응용 프로그램에서 구현할 수 있습니다 및 모든 응용 프로그램 놓기 소스, 놓기 대상 또는 둘 다를 수 있습니다. 놓기 소스와 대상 놓기 지원을 구현에 응용 프로그램을 자식 창 사이 또는 단일 창에서 끌어서 놓기 사용 됩니다. 이 기능은 수 훨씬 쉽게 사용할 수 없는 응용 프로그램을 확인 합니다.  
  
 OLE 끌어서 놓기 기능을 사용 하려는 경우 참조 [끌어서 놓기: 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다. 놓기 소스 비 OLE 응용 프로그램이 해당 문서에 설명 된 기술을 사용할 수 있습니다. 문서 [끌어서 놓기: 놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md) OLE 및 비 OLE 응용 프로그램 모두에 대 한 놓기 대상 지원을 구현 하는 방법을 설명 합니다. MFC OLE 샘플을 검사 하는 것이 도움이 될 수도 [OCLIENT](../visual-cpp-samples.md) 및 [HIERSVR](../visual-cpp-samples.md)합니다.  
  
 읽지 않은 경우는 [데이터 개체 및 데이터 소스 (OLE)](../mfc/data-objects-and-data-sources-ole.md) 아티클의 제품군을 만들려는 경우 지금 합니다. 이러한 문서에서는 데이터 전송 및 응용 프로그램에서 구현 하는 방법의 기본적인 사항을 설명 합니다.  
  
 드래그 앤 드롭 하는 방법에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [끌어서 놓기: 놓기 소스 구현](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [끌어서 놓기: 놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [끌어서 놓기: 사용자 지정](../mfc/drag-and-drop-customizing.md)  
  
## <a name="see-also"></a>참고 항목  
 [OLE](../mfc/ole-in-mfc.md)   
 [데이터 개체 및 데이터 소스(OLE)](../mfc/data-objects-and-data-sources-ole.md)

