const employees = {
    "Alice": ["Morning", "Afternoon", "Evening"],
    "Bob": ["Afternoon", "Morning", "Evening"],
    "Charlie": ["Evening", "Morning", "Afternoon"],
    "David": ["Morning", "Afternoon", "Evening"],
    "Eve": ["Evening", "Afternoon", "Morning"]
};

const days = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"];
let shifts = {};
let workCount = {};

// Initialize shifts & work tracking
days.forEach(day => {
    shifts[day] = { "Morning": [], "Afternoon": [], "Evening": [] };
});
Object.keys(employees).forEach(emp => workCount[emp] = 0);

// Assign shifts
days.forEach(day => {
    Object.keys(employees).forEach(emp => {
        if (workCount[emp] < 5) {
            for (let shift of employees[emp]) {
                if (shifts[day][shift].length < 2 && !Object.values(shifts[day]).flat().includes(emp)) {
                    shifts[day][shift].push(emp);
                    workCount[emp]++;
                    break;
                }
            }
        }
    });
});

// Display schedule
console.log("Final Schedule:");
days.forEach(day => {
    console.log(`\n${day}:`);
    Object.keys(shifts[day]).forEach(shift => {
        console.log(`  ${shift}: ${shifts[day][shift].join(", ") || "No employees assigned"}`);
    });
});
