# radix_sort

int getmax(long long int b[], int p){
    int d=0;
    for(int q=0;q<p;q++){
        if(d <= b[q]){
            d = b[q];
        }
    }
    return d;
}
void count_sort(long long int c[],int g,int h){
    // printf("gfhj");
    int count[10] = {0};
    long long int k[g];
    for(int f=0;f<g;f++){
        ++count[(c[f]/h)%10];
    }
    for(int f=1;f<=10;f++){
        count[f] = count[f]+count[f-1];
    }
    for(int f=g-1;f>=0;f--){
        k[--count[((c[f])/h)%10]] = c[f];
    }
    for(int f=0;f<g;f++){
        c[f] = k[f];
    }
}
void rad_sort(long long int ar[],int y){
    int max = getmax(ar,y);
    // printf("%d\n",max);
    for(int pos = 1;max/pos>0;pos = pos*10){
        count_sort(ar,y,pos);
        //printf("dfhgfh");
    }
}
