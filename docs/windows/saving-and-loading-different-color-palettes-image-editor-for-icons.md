---
title: 색상표 저장 및 서로 다른 로드 (아이콘에 대 한 이미지 편집기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b96411341baeb6abb75c44063072b94fae3ac6a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892321"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>다른 색상표 저장 및 로드(아이콘에 대한 이미지 편집기)
저장 하 고 포함 된 색 색상표 로드 [색을 사용자 지정한](../windows/customizing-or-changing-colors-image-editor-for-icons.md)합니다. (Visual Studio를 시작하면 기본적으로 가장 최근에 사용한 색 색상표가 자동으로 로드됩니다.)  
  
> [!TIP]
>  이미지 편집기에는 기본색 색상표를 복원하는 수단이 없으므로, 기본색 색상표를 standard.pal 또는 default.pal과 같은 이름으로 저장해 두면 쉽게 기본 설정을 복원할 수 있습니다.  
  
### <a name="to-save-a-custom-colors-palette"></a>사용자 지정 색 색상표를 저장하려면  
  
1.  **이미지** 메뉴 선택 **색상표 저장**합니다.  
  
2.  색상표를 저장할 디렉터리로 이동하고 색상표의 이름을 입력합니다.  
  
3.  **저장**을 클릭합니다.  
  
### <a name="to-load-a-custom-colors-palette"></a>사용자 지정 색 색상표를 로드하려면  
  
1.  **이미지** 메뉴 선택 **색상표 로드**합니다.  
  
2.  에 [색상표 로드 대화 상자](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)올바른 디렉터리로 이동 하 고 로드할 색상표를 선택 합니다. 색 색상표는 .pal 파일 확장명으로 저장됩니다.  
  

  
 요구 사항  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [색 작업](../windows/working-with-color-image-editor-for-icons.md)