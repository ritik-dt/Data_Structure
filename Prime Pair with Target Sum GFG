class Solution {
    public static HashSet<Integer> hs = new HashSet<>();
    public static ArrayList<Integer> getPrimes(int n) {
        // code here
        ArrayList<Integer> primesTillN = getAllPrimesTillN(n);
        ArrayList<Integer> ans = new  ArrayList<Integer>();
        for(int i=0; i<primesTillN.size(); i++){
            int curr = primesTillN.get(i);
            if(hs.contains(n-curr)){
                ans.add(curr);
                ans.add(n-curr);
                break;
            }
        }
        if(ans.size() == 0){
            ans.add(-1);
            ans.add(-1);
        }
        return ans;
        
    }   
    
    public static ArrayList<Integer> getAllPrimesTillN(int n){
        // seiev of eratosthenes
        ArrayList<Integer> primes = new ArrayList<Integer>();
        boolean[] isPrimes = new boolean[n+1];
        Arrays.fill(isPrimes, true);
        isPrimes[0] = false;
        isPrimes[1] = false;
        
        for(int i = 2; i*i <= n; i++){
            if(isPrimes[i]== true){
                for(int j = i*i; j <= n; j+=i){
                    isPrimes[j] = false;
                }
            }
        }
        
        for(int i =2; i<= n; i++){
            if(isPrimes[i] == true){
                primes.add(i);
                hs.add(i);
            }
        }
        return primes;
    }
    
}
