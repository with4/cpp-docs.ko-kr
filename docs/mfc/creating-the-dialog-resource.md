---
title: "대화 상자 리소스 만들기 | Microsoft Docs"
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
- dialog resources
- MFC dialog boxes [MFC], creating
- dialog templates [MFC], creating dialog resource
- templates [MFC], creating
- resources [MFC], creating dialog boxes
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 0b83bd33-14d3-4611-8129-fccdae18053e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c94bd3a31d74f2870ae2016bf734739da212c3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-dialog-resource"></a>대화 상자 리소스 만들기
디자인 하기 위해는 [대화 상자](../mfc/dialog-boxes.md) 대화 상자 리소스를 사용 하 고는 [대화 상자 편집기](../windows/dialog-editor.md)합니다. 대화 상자 편집기에서는 다음을 수행할 수 있습니다.  
  
-   대화 상자가 나타날 때 대화 상자의 크기 및 위치를 조정합니다.  
  
-   컨트롤 팔레트에서 여러 종류의 컨트롤을 끌어서 대화 상자에서 원하는 위치에 놓습니다.  
  
-   도구 모음에서 맞춤 단추를 사용하여 컨트롤을 배치합니다.  
  
-   프로그램에서 대화 상자에 지정할 모양 및 동작을 시뮬레이션하여 대화 상자를 테스트합니다. 테스트 모드에서는 텍스트 상자에 텍스트를 입력하고, 입력 단추를 클릭하는 등 대화 상자의 컨트롤을 조작할 수 있습니다.  
  
 작업을 마치면 대화 상자 템플릿 리소스가 응용 프로그램의 리소스 스크립트 파일에 저장됩니다. 필요한 경우 나중에 편집할 수 있습니다. 설명은 만들고 대화 상자 리소스를 편집 하는 방법에 대 한 참조는 [대화 상자 편집기](../windows/dialog-editor.md) 항목입니다. 이 기법에 대 한 대화 상자 템플릿 리소스를 만드는 데 수도 [CFormView](../mfc/reference/cformview-class.md) 및 [CRecordView](../mfc/reference/crecordview-class.md) 클래스입니다.  
  
 이 대화 상자의 모양이 적합 하면을 만든 다음 대화 상자 클래스에 설명 된 대로 메시지를 매핑합니다 [코드 마법사로 대화 상자 클래스 만들기](../mfc/creating-a-dialog-class-with-code-wizards.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

