---
title: "Marshaling | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM 인터페이스, marshaling"
  - "marshaling"
  - "marshaling, COM interop"
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Marshaling
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마샬링 COM 기술은 인터페이스를 노출의 객체에서 한 프로세스가 다른 프로세스에서 사용할 수 있습니다.  마샬링 COM 코드 제공 \(또는 인터페이스 구현자에 의해 제공 되는 코드를 사용 하 여\) 프로세스 \(그리고, 다른 컴퓨터에서 실행 중인 프로세스에 연결\)를 이동할 수 있는 형식으로 메서드의 매개 변수를 압축 하 고 압축을 풀려면 다른 끝에는 매개 변수입니다.  마찬가지로, COM 호출에서 반환에 이러한 동일한 단계를 수행 해야 합니다.  
  
> [!NOTE]
>  개체에서 제공 하는 인터페이스 객체와 같은 프로세스에서 사용 될 때 마샬링 일반적으로 필요 하지 않습니다.  그러나 마샬링 스레드 간에 필요할 수 있습니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)