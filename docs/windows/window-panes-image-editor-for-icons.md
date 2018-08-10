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
ms.openlocfilehash: a38341f6c6bcbcdec6bb4e6f5e5820fa759e6dab
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652027"
---
# <a name="window-panes-image-editor-for-icons"></a>창(아이콘에 대한 이미지 편집기)
합니다 **이미지 편집기** 창은 일반적으로 분할 막대로 구분 된 두 창에 이미지를 표시 합니다. 그 중 하나는 실제 크기 및 다른 확대 됩니다 (기본 확대 비율을이 6). 이러한 두 창의 뷰를 자동으로 업데이트 됩니다: 하나의 창에서 수행한 변경 내용에 다른 바로 표시 됩니다. 두 개의 창이 사용 하면 쉽게 더 크게 보려면 이미지를 수 있습니다 각 픽셀을 구분 하 고 있는, 동시에 이미지의 실제 크기 보기에서 작업의 효과 관찰의 작업할 수 있습니다.  
  
 필요한 만큼 많은 공간을 사용 하는 왼쪽된 창 (의 최대 절반를 **이미지** 창) 이미지를 기본값인 1:1 비율로 표시 합니다. 오른쪽 창 확대/축소 된 이미지 (기본적으로 6:1 비율로)를 표시 합니다. 할 수 있습니다 [배율을 변경](../windows/changing-the-magnification-factor-image-editor-for-icons.md) 사용 하 여 각 창에는 **확대** 도구를 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 또는 액셀러레이터 키를 사용 하 여 합니다.  
  
 더 작은 창을 확대할 수 있습니다 합니다 **이미지 편집기** 창 두 창을 사용 하 여 큰 이미지의 다른 영역을 표시 합니다. 선택 창에서 클릭 합니다.  
  
 분할 막대에 포인터를 놓고 오른쪽 또는 왼쪽 분할 막대를 이동 하 여 창의 상대적 크기를 변경할 수 있습니다. 분할 막대 하나의 창에서 작업 하려는 경우 어느 쪽으로 이동할 수 있습니다.  
  
 경우는 **이미지 편집기** 창은 4 비율로 확대 이상, 할 수 있습니다 [픽셀 모눈을 표시](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) 이미지의 개별 픽셀을 구분 하는 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)