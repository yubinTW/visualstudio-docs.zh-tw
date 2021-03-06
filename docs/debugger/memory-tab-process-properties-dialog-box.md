---
title: "記憶體索引標籤，處理序屬性對話方塊 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: Process properties for Windows NT
ms.assetid: a70785f2-5997-40ec-a90f-80a52449768b
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f846b66378f73239adf025d017e3553aaf6046a8
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/04/2018
---
# <a name="memory-tab-process-properties-dialog-box"></a>處理序屬性對話方塊、記憶體索引標籤
使用**記憶體** 索引標籤以顯示如何處理程序使用的記憶體。 若要顯示[處理序屬性對話方塊](../debugger/process-properties-dialog-box.md)，焦點移至[處理序檢視](../debugger/processes-view.md)視窗。 在樹狀目錄中，選取任何處理序節點，然後選擇 **屬性**從**檢視**功能表。  
  
 下列設定都適用於**記憶體** 索引標籤：  
  
|進入|描述|  
|-----------|-----------------|  
|**虛擬位元組**|處理序正在使用虛擬位址空間的目前大小 （以位元組為單位）。 使用虛擬位址空間不會不一定表示相應地使用磁碟或主記憶體分頁。 不過，虛擬空間很有限，而且使用太多可能會限制處理序載入程式庫的能力。|  
|**尖峰虛擬位元組**|在任何一個時間已使用的處理程序的虛擬位址空間的位元組數目上限。|  
|**工作集**|由程序中執行緒最近觸及的記憶體分頁的集合。 如果電腦中的可用記憶體超過閾值，即使未使用頁面會保留在處理程序的工作集中。 當可用記憶體低於臨界值時，會從工作集修剪頁面。 如果需要，將其寫回工作集之前離開主記憶體。|  
|**尖峰工作集**|此處理序在任何時間點的工作集中頁面的數目上限。|  
|**分頁集區位元組**|目前的處理序已配置的分頁集區容量。 分頁集區是系統記憶體區域，其中作業系統元件時，取得空間它們完成指定的工作。 分頁集區頁面可以分頁到分頁檔有持續一段時間未存取系統。|  
|**Pool nonpaged 的 Bytes**|目前的處理序配置的未分頁集區中的位元組數。 非分頁集區是系統記憶體區域位置取得空間的作業系統元件完成其指定的工作。 非分頁集區頁面不能移出分頁檔案。它們留在主記憶體，只要這些配置。|  
|**私用位元組**|目前此程序已配置的位元組數目不能與其他處理序共用。|  
|**可用的位元組**|此處理序的總未使用的虛擬位址空間。|  
|**保留的位元組**|此處理序所保留供未來使用的虛擬記憶體總數。|  
|**可用的映像位元組**|未使用，或此處理序內的影像所保留的虛擬位址空間數量。|  
|**保留的影像位元組**|執行此處理序內的影像所保留的所有虛擬記憶體的總和。|