# Intership
const chooseOptimalDistance = (t, k, ls) => {
    if(ls.length>=k)
    {
         let summ=[t];   
       do{
        let res=ls.reduce(function (sum, current, index){
            if(index<k)
            {
                 sum+=current;
            }
            return sum;
           },0);
           summ.push(res);
            ls.shift();
        }while(ls.length>=k)
 summ.sort((a, b) => a - b);
 let b= summ.indexOf(t);
 if(b==0)
 {
    return null;
 }
 else
 {
    return summ[b-1];
 }
 }
 return null;
}
 console.log( chooseOptimalDistance(174, 3, [51, 56, 58, 59, 61])); //173
 console.log(chooseOptimalDistance(163, 3, [50])); // null
