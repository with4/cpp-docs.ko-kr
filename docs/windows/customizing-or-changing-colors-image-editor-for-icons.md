---
title: "사용자 지정 색 또는 변경 (아이콘에 대 한 이미지 편집기) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- luminosity
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 762c2a9d9814f9780aeae2d8d61d7006bdc9728c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>색 사용자 지정 또는 변경(아이콘에 대한 이미지 편집기)
이미지 편집기의 [색상표](../windows/colors-window-image-editor-for-icons.md) 처음 16 개의 표준 색을 표시 합니다. 표시된 색 외에도 사용자 지정 색을 직접 만들 수 있습니다. 그런 다음 [저장 하 고 사용자 지정된 색상표 로드](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)합니다.  
  
### <a name="to-change-colors-on-the-colors-palette"></a>색상표에서 색을 변경하려면  
  
1.  **이미지** 메뉴 선택 **색 조정**합니다.  
  
2.  에 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), 적절 한 텍스트 상자에 RGB 또는 HSL 값을 입력 하 여 색을 정의 하거나에서 색을 선택는 **그라데이션 색 디스플레이** 상자입니다.  
  
3.  슬라이더를 이동 하 여 명도 설정의 **명도** 모음입니다.  
  
4.  많은 사용자 지정 색이 디더링됩니다. 디더링된 색에 가장 가까운 단색을 원하면 두 번 클릭은 **색** 상자입니다.  
  
     나중에 디더링된 색에서 슬라이더를 이동는 **명도** 가로 막대형 또는 십자에서 이동는 **그라데이션 색 디스플레이** 상자 하 여 디더링을 복원 합니다.  
  
5.  클릭 **확인** 새로운 색을 추가 합니다.  
  

  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)