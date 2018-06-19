---
title: 창 (아이콘에 대 한 이미지 편집기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e899729e70db089c1c55f00aa9c4196a22c67060
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892841"
---
# <a name="window-panes-image-editor-for-icons"></a>창(아이콘에 대한 이미지 편집기)
일반적으로 이미지 편집기 창 분할 막대로 구분 된 두 창에 이미지를 표시 합니다. 그 중 하나는 실제 크기 및 다른 확대 됩니다 (기본 확대 계수는 6). 이러한 두 창의 뷰를 자동으로 업데이트 됩니다: 하나의 창에서 수행한 변경 내용을 다른에 즉시 표시 됩니다. 두 개의 창이 쉽게 확대해 수 개별 픽셀을 구분 하 고 있는, 같은 시간에 이미지의 실제 크기 보기에서 작업의 효과 확인 합니다. 이미지에서 작업할 수 있습니다.  
  
 왼쪽된 창에는 만큼의 공간 이미지를 기본값인 1:1 비율로 표시 합니다 (최대 크기의 절반 이미지 창)을 필요에 따라 사용 합니다. 오른쪽 창에는 확대/축소 된 이미지 (기본적으로 6:1 비율로) 표시 됩니다. 할 수 있습니다 [배율을 변경](../windows/changing-the-magnification-factor-image-editor-for-icons.md) 사용 하 여 각 창에는 **확대** 도구에 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 또는 액셀러레이터 키를 사용 하 여 합니다.  
  
 이미지 편집기 창의 더 작은 창 확대 수 있으며 두 개의 창이 사용 하 여 큰 이미지의 서로 다른 지역 표시할 수 있습니다. 선택 창에서를 클릭 합니다.  
  
 분할 막대에 포인터를 두고 오른쪽 또는 왼쪽 분할 막대를 이동 하 여 창의 상대적 크기를 변경할 수 있습니다. 분할줄 하나의 창에서 작업 하려는 경우 어느 쪽으로 이동할 수 있습니다.  
  
 이미지 편집기 창이 4 이상이의 비율로 확대 되 면 다음을 할 수 있습니다 [픽셀 모눈을 표시](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) 이미지의 개별 픽셀을 구분 하는 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)

