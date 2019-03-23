##数组排序
###1-冒泡排序
    var arr = [9,8,7,6,5,4,3,2,1];
	var temp;
	for(var i = 0; i < arr.length; i++){
		for(var j = 0; j < arr.length - i; j++){
			if(arr[j] > arr[j+1]){//从第零个数开始,依次将每个数和后一个数比大小,将最大的数换到最后一个
				temp = arr[j+1];
				arr[j+1] = arr[j];
				arr[j] = temp;
			}	
		}//一次内层循环完毕后只能将一个最大的数放到最后,需要外层循环来重新启动内层循环,每次将未排序的数中最大的数放到未排序的数的最后,
		console.log(arr);
	}	
###2-选择排序
	var arr = [9,8,7,6,5,4,3,2,1];
	var temp,min;
	for(var i = 0; i < arr.length - 1; i++){
		for(var j = i+1; j < arr.length; j++){
			min = i;
			if(arr[j] < arr[min]){//如果arr[j]比arr[min]小,
				min = j;          //就将arr[j]的下标赋给min,然后j++,再和arr[min]比大小,直到最后一个数,min就是最小数的下标,arr[min]就是最小数
			}//if比较结束后,原数组还没有发生变化,因为min是在i与j之外的,只是用来暂存最小数下标的,
            
            //这里,才开始将 arr[i] 和 arr[min] 换位置(与冒泡排序不同的是,只需要换一次位置就可以);
			temp = arr[i];
			arr[i] = arr[min];
			arr[min] = temp;
		}	
	}
