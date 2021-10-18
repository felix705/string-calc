# string-calc

@@ -0,0 +1,49 @@

const stringCalc = (nums) => {
    if (nums === "") {
        return 0;
    } else {
        const string = "1\n2,3";
        let result1 = string.split("\n");
        result1 = string.split(',');
        // const listOfNums = nums.split(",");
        const listOfNums = result1;

        let result = 0;
        listOfNums
            .map((num) => parseInt(num))
            .forEach((num) => result += num)
        // const a = parseInt(listOfNums[0]);
        // const b = parseInt(listOfNums[1]);
        // return a + b;
        return result;
    }
}

describe('string-calc', () => {
    it('The method takes up two numbers and returns their sum', () => {
        const nums = "1,2";
        const result = stringCalc(nums);
        expect(result).toBe(3);
    })
    it('The method has an empty string and returns 0', () => {
        const nums = "";
        const result = stringCalc(nums);
        expect(result).toBe(0);
    })
    it('The method takes up two numbers and returns their sum', () => {
        const nums = "4,7";
        const result = stringCalc(nums);
        expect(result).toBe(11);
    })
    it('The method takes up three numbers and returns their sum', () => {
        const nums = "1,2,3";
        const result = stringCalc(nums);
        expect(result).toBe(6);
    })
    it('The method should handle new lines between numbers (instead of commas)', () => {
        const nums = "1\n2,3";
        const result = stringCalc(nums);
        expect(result).toBe(6);
    })
})
