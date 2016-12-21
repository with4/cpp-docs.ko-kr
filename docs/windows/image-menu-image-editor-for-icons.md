---
title: "이미지 메뉴(아이콘에 대한 이미지 편집기) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.bitmap"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "이미지 메뉴"
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이미지 메뉴(아이콘에 대한 이미지 편집기)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이미지 편집기를 실행할 때만 표시되는 이미지 메뉴에는 이미지 편집, 색상표 관리 및 이미지 편집기 창 옵션 설정에 대한 명령이 있습니다.  또한, 아이콘과 커서 작업을 할 때는 장치 이미지 사용에 대한 명령도 사용할 수 있습니다.  
  
 **색 반전**  
 색을 반전합니다.  자세한 내용은 [선택 영역에서 색 반전](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)을 참조하십시오.  
  
 **좌우 대칭**  
 이미지나 선택 영역을 좌우 대칭 이동합니다.  자세한 내용은 [이미지 대칭 이동](../mfc/flipping-an-image-image-editor-for-icons.md)을 참조하십시오.  
  
 **상하 대칭**  
 이미지나 선택 영역을 상하 대칭 이동합니다.  자세한 내용은 [이미지 대칭 이동](../mfc/flipping-an-image-image-editor-for-icons.md)을 참조하십시오.  
  
 **90도 회전**  
 이미지나 선택 영역을 90도 회전합니다.  자세한 내용은 [이미지 대칭 이동](../mfc/flipping-an-image-image-editor-for-icons.md)을 참조하십시오.  
  
 **색상 창 표시**  
 이미지에 사용할 색을 선택할 수 있는 [색상 창](../windows/colors-window-image-editor-for-icons.md)을 엽니다.  자세한 내용은 [색 작업](../mfc/working-with-color-image-editor-for-icons.md)을 참조하십시오.  
  
 **선택 항목을 브러시로 사용**  
 이미지의 일부를 사용자 지정 브러시로 만듭니다.  그러면 선택 영역은 이미지의 선택 영역에 색을 분사하는 사용자 지정 브러시가 됩니다.  그리고 끌기 경로에 선택 영역의 복사본이 생깁니다.  느리게 끌수록 많은 복사본이 만들어집니다.  자세한 내용은 [사용자 지정 브러시 만들기](../mfc/creating-a-custom-brush-image-editor-for-icons.md)를 참조하십시오.  
  
 **선택 항목 복사 및 윤곽선 그리기**  
 현재 선택한 항목의 복사본을 만들고 윤곽선을 그립니다.  [투명](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)을 선택한 경우, 현재 선택 영역에 배경색이 포함되었으면 배경색은 제외됩니다.  
  
 **색 조정**  
 이미지에 사용할 색을 사용자 지정할 수 있는 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)를 엽니다.  자세한 내용은 [색 사용자 지정 또는 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)을 참조하십시오.  
  
 **색상표 로드**  
 이전에 .pal 파일에 저장한 색상표 색을 로드할 수 있는 [색상표 로드 대화 상자](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)를 엽니다.  
  
 **색상표 저장**  
 .pal 파일에 색상표 색을 저장합니다.  
  
 **불투명하게 그리기**  
 이 메뉴를 선택하면 현재 선택 영역이 불투명해집니다.  선택을 취소하면 현재 선택 영역이 투명해집니다.  자세한 내용은 [투명 또는 불투명 배경 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)을 참조하십시오.  
  
 **도구 모음 편집기**  
 [새 도구 모음 리소스 대화 상자](../mfc/new-toolbar-resource-dialog-box.md)를 엽니다.  
  
 **모눈 설정**  
 이미지에 모눈을 지정할 수 있는 [모눈 설정 대화 상자](../mfc/grid-settings-dialog-box-image-editor-for-icons.md)를 엽니다.  
  
 **새 이미지 형식**  
 [새 \<Device\> 이미지 형식 대화 상자](../mfc/new-device-image-type-dialog-box-image-editor-for-icons.md)를 엽니다.  하나의 아이콘 리소스에 크기가 서로 다른 여러 이미지를 포함할 수 있고, 창은 이미지 표시 방법에 따라 원하는 아이콘 크기를 사용할 수 있습니다.  새 장치 유형에 따라 아이콘 크기가 변경되지는 않지만 아이콘 내에 새 이미지를 만듭니다.  이 메뉴는 아이콘과 커서에만 적용됩니다.  
  
 **현재 아이콘\/커서 이미지 형식**  
 사용할 수 있는 처음 9개의 커서나 아이콘 이미지가 표시된 하위 메뉴를 엽니다.  하위 메뉴의 마지막 명령인 **추가 아이콘...**을 선택하면 [\<Device\> 이미지 열기 대화 상자](../mfc/open-device-image-dialog-box-image-editor-for-icons.md)가 열립니다.  
  
 **이미지 형식 삭제**  
 선택된 장치 이미지를 삭제합니다.  
  
 **도구**  
 [이미지 편집기 도구 모음](../mfc/toolbar-image-editor-for-icons.md)에서 사용할 수 있는 모든 도구가 들어 있는 하위 메뉴를 실행합니다.  
  
## 요구 사항  
 없음  
  
## 참고 항목  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Image Editor for Icons](../mfc/image-editor-for-icons.md)